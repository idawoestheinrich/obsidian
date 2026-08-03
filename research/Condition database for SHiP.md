
title: Introduction to SHiP's Condition Database (CondDB)
shorttitle: SHiP's Condition Database
institute: European Organization for Nuclear Research
shortinstitute: CERN
author:
	- Ole Martin Ruud
	- Enrico Gamberini
date: 2025-09-19
lang: en-US
...

## What is a Condition Database

- Store and retrieve conditions.
- Conditions relevant in a given *time frame* or *interval*.
- Examples:
	- __during data taking__: detector configuration, beam intensity, temperature of sensors, bias voltage of whatever, etc.
	- __during simulation__: all configurations used to produce the simulated data
- Currently configurations are stored in files, committed to GitHub.
- Jobs to produce or analyze data will need a copy of those conditions.
- *Conditions* can be anything we want it to be really.

## What is a Condition Database

> Provides a scalable way for __thousands__ of jobs to concurrently pull
> __only the relevant condition files__ needed to run simulation,
> *reconstruction*, and *analysis* without the need for local copies of all of
> the files.

## SHiP's Condition Database

- Modernized and simplified implementation of [HSF Reference Database][hsf_referencedb].
- Based on work of HSF working group [@laycock2019hep].
- Separating conditions from metadata enables high throughput.
- Backend written in [Rust] using a [PostgreSQL] database.
- Client library with multiple language bindings (Rust, C++ and Python).

[nopayloaddb]: https://github.com/BNLNPPS/nopayloaddb
[cond_data_mgmt]: https://indico.cern.ch/event/567550/papers/2627129/files/6300-laycock_ACAT17.pdf
[hsf_referencedb]: https://indico.cern.ch/event/1369601/contributions/5883610/attachments/2856375/4995949/conditions_db_reference_implementation_hsf_2024.pdf
[Rust]: https://www.rust-lang.org/
[PostgreSQL]: https://www.postgresql.org/

---

![NPDB Architecture](./docs/images/npdb-arch.drawio.pdf)

## Current Status

- [Deployed on CERNs OpenShift PaaS platform][deployment].
- Client library added and linked to FairShip.
- Goal to submit the first payloads from simulations soon.

[deployment]: https://npdb-api-ship-dev-rs.app.cern.ch/

# Questions?

## Important Terms

- **Interval of Validity** - The time frame in which conditions are valid
- **Global Tag** - A name for a collection of related conditions
- **Payload Type** - A name for a certain type of conditions
- **Payload Group** - A group of similar conditions within a global tag

## Authentication

- Locally generated access tokens
- Currently a CERN Computing Account needed to generate tokens
- Access token valid for 24 hours, can be refreshed for 1 week
- A script provided to generate the tokens `npdb-get-local-tokens.sh`

## References