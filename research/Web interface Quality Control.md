[Easy webinterface - no liveplots - streamlit](https://streamlit.io/playground?example=charts) 

Web interface recommended by Christian: [[Django app]]
>Ich hab vor einer Weile eine Web-Application für ITK-Strips programmiert. Nach einer Menge Research bin ich zu Django konvergiert: [https://www.djangoproject.com/](https://www.djangoproject.com/). 
>Großartig, einfach und sehr gut dokumentiert. Mit einem guten Tutorial, das alles gut zusammenfasst, und eingebautem Database Management. SQLite könntest du direkt im CERN-Webservice hosten.  Bezüglich CERN hab ich das hier benutzt: [https://paas.docs.cern.ch/](https://paas.docs.cern.ch/)

  

Liebe Grüße

Christian
- Start and end of the measurement 
- Data saving (Ask for the name of the WOM tube and save the data to a file)
	- It would be cool if one could klick on one measurement in the past and directly see the heatmap and a number for the overall quality
- Display heatmaps - response, transmission and (maximal ? ) standard deviation for both
- Display 3 waveforms? 1 PMT, 2 SiPMs
- Safe waveforms? On off
- Can the web interface display the MotionSoft window to look at the position of the LED
- Display temperature? 
- Safe temperature
- When we have a standard - pass or fail? 


# # # #  1. Global status (always visible)
- **Connection status**
- **System state**
	- Idle / Moving / Measuring / Error / Emergency stop
- **Current position?** 
- **Big red E-STOP indicator** (even if physical one exists)
# # #  2. Measurement control
- Start / stop / pause measurement - option to stop the measurement
- Measurement mode selection?
- Setting/displaying parameters of the measurement 
- Estimated duration display
- Progress bar + current step
# # #  3. Live data visualization
- Live plots (signal vs time, signal vs position)
	- PMT, SiPMin, SiPMout
	- Display data quality flags
# #  6. Data handling
Don’t make users hunt for their data.
- Automatic file naming (timestamp + metadata)
- Download links
- Export formats (CSV, HDF5, ROOT, etc.)
- Run history with quick re-load
Very useful:
- “Repeat last run”
- “Clone and modify”

#  How app is structured

app -
- data
- main.py 
	- blueprints (so not everything has to be done in one file): 
		- `Flask app` → the house
		- `Blueprints` → rooms
		- `Routes` → furniture inside each room
	- app, socketio
	- routes.routes_bp
	- auth.auth_pb
- test_usb_webapp.ino 
	- "PIN_ON" and "PIN_OFF"
- app
	- `__init__.py` 
		- imports Flask/SocketIO but also from app.auth auth_bp, login_manager
	- auth.py
		- imports Blueprint, request, redirect, url_for, render_template, flash
		- LoginManager, login_user, login_required, UserMixin, current_user
		- defines a User class
		- def login: 
		- def logout
	- routes.py 
		- ```python	
				from app import app, socketio
			  	from app.auth import login_required
			  	from app.utils import arduino, frequency_data,
			  	 save_data_to_file
		```
		- Defines a data folder
		- browse directory 
		- download file
		- index - “Whenever someone goes to `/` (the homepage), call the function `index()`.”
		-  control arduino  - appends data to frequency_data
		- get data - jsonify the data - sends the data to the browser - to plot them
		- enable_save - sets  save_to_file["enabled"] = True
		- def disable_save():
	
	- utilitis.py
		- set serialport and baud_rate
		- trys to connect to arduino 
		- save_data_to_file
	- `__pycache__`
	- static
		- css - defines styles
		- js 
			- Display and download data (*browseDirectory()*)
			- Produces plots (await fetch, await response.json())
			- Save data
	- templates
		- index.html () - defines the looks of the webside
		- login.html() - defines how the login page should look like


