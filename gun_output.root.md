Dataframe from datasource RNTupleDS

Property                Value
--------                -----
Columns in total           11
Columns from defines        0
Event loops run             0
Processing slots            1

Column                          Type                                            Origin
------                          ----                                            ------
event_header                    SHiP::EventHeader                               Dataset
event_header.original_event_id  std::int64_t                                    Dataset
event_header.weight             double                                          Dataset
mc_particles                    ROOT::VecOps::RVec<SHiP::MCParticle>            Dataset
mc_particles.energy             ROOT::VecOps::RVec<double>                      Dataset
mc_particles.momentum           ROOT::VecOps::RVec<ROOT::VecOps::RVec<double>>  Dataset
mc_particles.motherId           ROOT::VecOps::RVec<std::int32_t>                Dataset
mc_particles.pdgCode            ROOT::VecOps::RVec<std::int32_t>                Dataset
mc_particles.status             ROOT::VecOps::RVec<std::int32_t>                Dataset
mc_particles.time               ROOT::VecOps::RVec<double>                      Dataset
mc_particles.vertex             ROOT::VecOps::RVec<ROOT::VecOps::RVec<double>>  Dataset
root [3] df.Display()->Print();
Info in <Print>: Only showing 5 columns out of 12

+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
| Row | event_header    | event_header.original_event_id | event_header.weight | mc_particles    | ... | 
+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
| 0   | @0x56531fb5db30 | -1                             | 1.000000            | @0x565320420390 | ... | 
+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
| 1   | @0x56531fb5db30 | -1                             | 1.000000            | @0x565320420390 | ... | 
+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
| 2   | @0x56531fb5db30 | -1                             | 1.000000            | @0x565320420390 | ... | 
+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
| 3   | @0x56531fb5db30 | -1                             | 1.000000            | @0x565320420390 | ... | 
+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
| 4   | @0x56531fb5db30 | -1                             | 1.000000            | @0x565320420390 | ... | 
+-----+-----------------+--------------------------------+---------------------+-----------------+-----+
root [4] 
root [4] // Print specific variables for the first 10 events
root [5] df.Display({"px", "py", "pz"}, 10)->Print();.q
ROOT_prompt_5:1:45: error: expected expression
df.Display({"px", "py", "pz"}, 10)->Print();.q