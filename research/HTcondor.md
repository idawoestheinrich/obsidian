- [Website](https://batchdocs.web.cern.ch/local/quick.html)
- [Introduction to HTCondor]( https://indico.kit.edu/event/196/contributions/673/attachments/475/744/02_HTCondor_ALahiff.pdf)
- Job flavors - f.e. "next week", "testmatch"
- Maxruntime in seconds

- [github Anupama](https://github.com/anupama-reghunath/HTCondor_scripts/tree/main/MuonBack)

```shell
condor_submit <filename>.sub
```

To see how its going
```shell
condor_q 
```

Remove job - `shift+command+c` copy in der console
```
condor_rm <cluster id>
```

Katharinas two templates in 
`/Users/ida/Desktop/Research/ship/code/condor_ana_sub`