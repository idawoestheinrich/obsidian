work from your aft/work directory. 
Open:
```
/afs/cern.ch/work/<first_letter_username>/<username>/
```

Assign the directory of pixi to your work directory by running 
```bash
export PATH="/afs/cern.ch/work/<first_letter_username>/<username>//.pixi/bin:$PATH"
export PIXI_HOME=/afs/cern.ch/work/<first_letter_username>/<username>//.pixi
export PIXI_CACHE_DIR=/afs/cern.ch/work/<first_letter_username>/<username>//.cache
```
[Install pixi](https://pixi.prefix.dev/latest/installation/#installer-script-options): 
On Mac/linux
```
curl -fsSL https://pixi.sh/install.sh | sh
```
if that does not work follow instructions on the pixi website

Clone the git repository of [[Aegir]] - [documentation](https://shipsoft.github.io/Documentation/simulation/) and build with pixi:
```
git clone https://github.com/ShipSoft/aegir.git
cd aegir
pixi run build
```
Simulate your first dataset:
```
pixi run phlex -c workflows/pythia8_mt.jsonnet
```