### Gitlab for testbeam analysis
- with hannes
### Software for the file name and table coordinates
- Little program that writes table coordinates and file names into a table 
- **Input:** 
	- CellName
	- Position on the Cell in cell coordinates
	- Angle
	- Cell orientation horizontal or vertical?
	- Table coordinate center (X, Y), minimum and maximum in X and Y
	- Order by which value - X, Y rotation 
		- Least changes per measurement
- **Output:** 
	- file name with 
		- measurement number
		- date
		- CellName
		- XCoordinate
		- YCoordinate
		- Rotation
	- Table coordinates
		- XCoordinate
		- YCoordinate
		- Rotation
	- Visualisation of the points on the detector cell 
		- with measurement number
		- Cell coordinates
		- Table coordinates

**If vertical:** 
- at 0 degrees 
	- X_table= X_cell+X_table_center
	- Y_table= Y_cell+Y_table_center
- at 180 degrees 
	- X_table= -X_cell-X_table_center
	- Y_table= Y_cell+Y_table_center
**If horizontal:** 
- at 0 degrees 
	- X_table= Y_cell+Y_table_center
	- Y_table= X_cell+X_table_center
- at 180 degrees 
	- X_table= -Y_cell-Y_table_center
	- Y_table= X_cell+X_table_center
- In rotation the position is supposed to hit the cell in the center (10cm deep) of the position on the Cell in cell coordinates
- If a position can not be reached because X_table_max is to small rotate 180 degrees to hit the cell on the other side in this position 
- If position can not be reached in any case - return a little note on that