### Variable Descriptions

#### 1. `event_header` (Global Event Metadata)
- **`event_header.original_event_id`**: The event index assigned by the primary generator.
- **`event_header.weight`**: Monte Carlo statistical weight assigned to the event for cross-section calculations and reweighting.

#### 2. `sim_hits` (Detector Responses)

These record actual **energy deposits** in active detector elements (scintillators, drift tubes, calorimeters):
- **`sim_hits.detectorId`**: Unique identifier for the active detector sub-system (e.g., veto wall, spectrometer, calorimeter).
- **`sim_hits.geometryNodeId`**: Specific geometric volume index inside Geant4.
- **`sim_hits.energyDeposit`**: Total ionization/energy absorbed by the detector material at that point (GeV).
- **`sim_hits.pathLength`**: Distance traveled by the particle while passing inside that volume element.
- **`sim_hits.position`**: Spatial coordinates (x,y,z) where the hit occurred.
- **`sim_hits.trackId`**: The `sim_particles.trackId` of the particle that produced this specific hit (used to link detector signals back to the particle).

#### 3. `sim_particles` Specific Fields
- **`sim_particles.trackId`**: Unique integer ID for each particle track produced in Geant4.
- **`sim_particles.parentId`**: The `trackId` of the parent particle that created this track (`0` or `-1` means it was a primary particle).
- **`sim_particles.creatorProcess`**: Geant4 physics process ID that created the particle (e.g., photo-electric effect, decay, inelastic scattering).
- **`sim_particles.endpoint`**: The (x,y,z) position where the particle stopped, left the world volume, or decayed.