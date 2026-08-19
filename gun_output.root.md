This output gives you the **schema (blueprint)** of your simulation output and a **preview of the actual event data**.

**1. `df.Describe().Print();` — The File Schema**
This lists every data column available in `gun_output.root`:

- **`event_header`**: Metadata for the overall event (e.g., event weight and ID).
- **`mc_particles`**: The simulated Monte Carlo particles generated in each event. Because one event can contain multiple particles, these are stored as arrays (`ROOT::VecOps::RVec`):
    - **`mc_particles.pdgCode`**: The particle type identifier (e.g., `11` = electron, `13` = muon, `22` = photon, `211` = pion).
    - **`mc_particles.energy`**: Energy of each particle in the event.
    - **`mc_particles.momentum`**: 3D/4D momentum vector array (px​,py​,pz​).
    - **`mc_particles.vertex`**: Creation coordinates (x,y,z) of each particle.
    - **`mc_particles.motherId`**: Index of the parent particle that produced it.
        
**2. `df.Display()->Print();` — The Data Preview**

This prints a table showing the first 5 rows (Events 0 through 4):
- The `@0x56531...` values are memory addresses pointing to full C++ objects (`SHiP::EventHeader` and `ROOT::VecOps::RVec`).
    
- ROOT displays memory pointers here because full C++ structures cannot be rendered as simple text numbers in a flat table.

