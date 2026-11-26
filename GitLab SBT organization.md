
- make the group easier to navigate 
- clear access and contribution rules
- **GitLab as the project and knowledge-management platform, and CERN storage (EON/EOS) as the place for actual experimental data and large files**
- 
1. **Scope:** SBT GitLab group as the central place for SBT-related software, documentation and technical work?
2. **Structure:** Organizing repositories by working area?
3. **Access:** Should all SHiP members retain read access to all repositories?
4. **Ownership:** Should every repository have designated maintainers and clearly defined contribution rules?
5. **Migration:** Should we actively encourage existing SBT-related code bases to move into the group?
6. **Infrastructure:** Mattermost?

## Agree on the scope and access policy: 
1. **GitLab:** code, documentation, procedures, configuration files, analysis scripts and metadata.
2. **EOS:** raw data, reconstructed data, simulation outputs, measurement files and large datasets.
3. **Wiki:** instructions explaining how these resources fit together and how to use them.

## New repository structure
```
- collaboration - (main branch unprotected?)
	- collaboration_meetings 
	- documentation

- software 
	- simulation
	- testbeam analysis
	

- detector_development
	- mechanics
	- electronics  
	- woms 
		- production
		- aging 
		- quality control 
	- liquid_scintillator
	- reflectivity
	  
— testing-and-commissioning	
	- cosmics_setup
	- testbeams
	  	- eurolabs
	  
- papers-and-talks  - (main branch unprotected?)
	- annual report
	- talks  	  
```


## GitLab Wiki
The Wiki should be the entry point for anyone joining the SBT collaboration or looking for existing technical material.

|Wiki section|Content|
|---|---|
|Getting started|How to access and use the SBT GitLab group|
|Repository structure|Explanation of repositories and where things belong|
|Contribution guidelines|Branching, commits, merge requests and reviews|
|Access and permissions|Who can read, write and maintain repositories|
|Documentation guidelines|File formats, Git LFS and naming conventions|
|Software guidelines|Coding standards, testing and CI practices|
|Project overview|Active projects, maintainers and contacts|
|Meeting documentation|How to upload agendas, minutes and presentations|

## Integrate GitLab notifications with Mattermost