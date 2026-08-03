# Autonomous Control and Data Acquisition System
Constellation is a control and data acquisition system for small-scale experiments and experimental setup with volatile and dynamic constituents such as testbeam environments or laboratory test stands.

- [[Constellation-The autonomous control and data acquisition system for dynamic experimental setups]]

- Look at the Tutorial pdf
	- *BTTB_Tutorial_Instructions.pdf*
- Additional commants
```

CXX=/usr/bin/clang++ CC=/usr/bin/clang meson setup build      
unset LDFLAGS 
unset LD 


source /Users/ida/Desktop/Research/conferences/BTTB2026/venv/bin/activatebash      
cd constellation 
env       
meson compile -C build   
meson setup build -Dwerror=false
meson install -C build  


/usr/local/bin/MissionControl

/usr/local/bin/TelemetryConsole
  ```