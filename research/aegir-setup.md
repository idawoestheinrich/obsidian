log into lxplus an run in terminal
```bash
export PATH="/afs/cern.ch/work/i/idwoesth/.pixi/bin:$PATH"
export PIXI_HOME=/afs/cern.ch/work/i/idwoesth/.pixi
export PIXI_CACHE_DIR=/afs/cern.ch/work/i/idwoesth/.cache
```
go into the aegir file and run 
```
pixi run build
```

```
git clone https://github.com/ShipSoft/aegir.git
cd aegir
pixi run build
pixi run phlex -c workflows/pythia8_mt.jsonnet
```