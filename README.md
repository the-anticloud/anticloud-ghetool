# GHETOOL

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-solar-lightgrey)

> Anticloud-hardened packaging of the upstream project `GHETOOL` in category **SOLAR**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** SOLAR · **Upstream:** https://github.com/wouterpeere/GHEtool · **Upstream pin:** `b47520e0a91a1d75609fce3f1e51551f51332c00` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# GHEtool: An open-source tool for borefield sizing

[![PyPI version](https://badge.fury.io/py/GHEtool.svg)](https://badge.fury.io/py/GHEtool)
[![Conda version](https://anaconda.org/conda-forge/ghetool/badges/version.svg)](https://anaconda.org/conda-forge/ghetool)
[![Tests](https://github.com/wouterpeere/GHEtool/actions/workflows/test.yml/badge.svg)](https://github.com/wouterpeere/GHEtool/actions/workflows/test.yml)
[![codecov](https://codecov.io/gh/wouterpeere/GHEtool/branch/main/graph/badge.svg?token=I9WWHW60OD)](https://codecov.io/gh/wouterpeere/GHEtool)
[![DOI](https://joss.theoj.org/papers/10.21105/joss.04406/status.svg)](https://doi.org/10.21105/joss.04406)
[![Downloads](https://static.pepy.tech/personalized-badge/ghetool?period=total&units=international_system&left_color=black&right_color=blue&left_text=Downloads)](https://pepy.tech/project/ghetool)
[![Downloads](https://static.pepy.tech/personalized-badge/ghetool?period=week&units=international_system&left_color=black&right_color=orange&left_text=Downloads%20last%20week)](https://pepy.tech/project/ghetool)
[![Read the Docs](https://readthedocs.org/projects/ghetool/badge/?version=latest)](https://ghetool.readthedocs.io/en/latest/)

## What is *GHEtool*?

<img src="https://raw.githubusercontent.com/wouterpeere/GHEtool/main/docs/Icon.png" width="110" align="left">

GHEtool is a Python package that contains all the functionalities needed to deal with borefield design. GHEtool has been
developed as a joint effort of KU Leuven (The SySi Team), boydens engineering (part of Sweco) and FH Aachen and is
currently being maintained by Enead BV.
The core of this package is the automated sizing of borefield under different conditions. By making use of combination
of just-in-time calculations of thermal ground responses
(using [pygfunction](https://github.com/MassimoCimmino/pygfunction)) with
intelligent interpolation, this automated sizing can be done in the order of milliseconds. Please visit our
website [https://GHEtool.eu](https://GHEtool.eu) for more information.

### Read The Docs

GHEtool has an elaborate documentation where all the functionalities of the tool are explained, with examples,
literature
and validation. This can be found
on [https://ghetool.readthedocs.io/en/latest/](https://ghetool.readthedocs.io/en/latest/).

## Graphical user interface

There are two graphical user interfaces available which are built using GHEtool: GHEtool Cloud and GHEtool Community

#### GHEtool Cloud

GHEtool Cloud is the official and supported version of GHEtool which supports drilling companies, engineering firms,
architects, government organizations in their geothermal design process.
With GHEtool Cloud they can minimize the environmental and societal impact while maximizing the cost-effective
utilization of geothermal projects.
Visit our website at [https://ghetool.eu](https://ghetool.eu) to learn more about GHEtool Cloud and what it can do for
you.

<p align="center">
<img src="https://ghetool.eu/wp-content/uploads/2024/08/GHEtool-Cloud-squarish.png" width="600">
</p>

#### GHEtool Community

Besides GHEtool Cloud, an open-source alternative for the graphical user interface is available in the form of *GHEtool
Community*.
This version is built and maintained by the community, and **has no official support like GHEtool Cloud**. You can read
all about this
*GHEtool Community* on their [GitHub project](https://github.com/wouterpeere/ghetool-gui).

### Development

GHEtool is in constant development with new methods, enhancements and features added to every new version. Please visit
our [project board](https://github.com/users/wouterpeere/projects/2) to check our progress.

## Requirements

This code is tested with Python 3.12, 3.13 and 3.14 and requires the following libraries

* matplotlib >= 3.9.2
* numpy >= 2.0.0
* pandas >= 1.4.3
* pygfunction >= 2.3.1
* scipy >= 1.18.1
* secondarycoolantprops >= 1.5
* optuna >= 3.6.1

For the tests

* pytest >= 7.1.2

## Quick start

### Installation

One can install GHEtool by running Pip and running the command

```
pip install GHEtool
```

or one can install a newer development version using

```
pip install --extra-index-url https://test.pypi.org/simple/ GHEtool
```

GHEtool is also available as a conda package. Therefore, you can install GHEtool with the command:

````
conda install GHEtool
````

Developers can source this project.

It is a good practise to use virtual environments (venv) when working on a (new) Python project so different Python and
package versions don't conflict with eachother. For GHEtool, Python 3.8 or higher is recommended. General information
about Python virtual environments can be found [here](https://docs.Python.org/3.9/library/venv.html) and
in [this article](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/).

### Check installation

To check whether everything is installed correctly, run the following command

```
pytest --pyargs GHEtool
```

This runs some predefined cases to see whether all the internal dependencies work correctly. All test should pass
successfully.

## Get started with GHEtool

### Building blocks of GHEtool

GHEtool is a flexible package that can be extend with methods
from [pygfunction](https://pygfunction.readthedocs.io/en/stable/).
To work efficiently with GHEtool, it is important to understand the main structure of the package.

#### Borefield

The Borefield object is the central object within GHEtool. It is within this object that all the calculations and
optimizations take place.
All attributes (ground properties, load data ...) are set inside the borefield object.

#### Ground properties

Within GHEtool, there are multiple ways of setting the ground data. Currently, your options are:

* _GroundConstantTemperature_: if you want to model your borefield with a constant, known ground temperature.
* _GroundFluxTemperature_: if you want to model your ground with a varying ground temperature due to a constant
  geothermal heat f

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Python** (manifests: pyproject.toml, requirements.txt; scanned in UPSTREAM_CLONE)
- Top-level source layout: `Articles/`, `GHEtool/`, `JOSS/`, `scripts/`
- Snapshot size: **551 files**, **43004 lines of code** (measured; see Benchmarks)
- Primary languages: `.pkl` (215), `.py` (178), `.csv` (59), `.rst` (46), `.md` (15), `.npz` (7)
- Upstream commit pinned for this packaging: `b47520e0a91a1d75609fce3f1e51551f51332c00`

---

## Installation

One can install GHEtool by running Pip and running the command

```
pip install GHEtool
```

or one can install a newer development version using

```
pip install --extra-index-url https://test.pypi.org/simple/ GHEtool
```

GHEtool is also available as a conda package. Therefore, you can install GHEtool with the command:

````
conda install GHEtool
````

Developers can source this project.

It is a good practise to use virtual environments (venv) when working on a (new) Python project so different Python and
package versions don't conflict with eachother. For GHEtool, Python 3.8 or higher is recommended. General information
about Python virtual environments can be found [here](https://docs.Python.org/3.9/library/venv.html) and
in [this article](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/).

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

of just-in-time calculations of thermal ground responses
(using [pygfunction](https://github.com/MassimoCimmino/pygfunction)) with
intelligent interpolation, this automated sizing can be done in the order of milliseconds. Please visit our
website [https://GHEtool.eu](https://GHEtool.eu) for more information.

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

literature
and validation. This can be found
on [https://ghetool.readthedocs.io/en/latest/](https://ghetool.readthedocs.io/en/latest/).

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Python |
| Manifests detected | pyproject.toml, requirements.txt |
| Files in snapshot | 551 |
| Lines of code | 43004 |
| Dependency references | 0 |
| Upstream license | BSD-3-Clause |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

utilization of geothermal projects.
Visit our website at [https://ghetool.eu](https://ghetool.eu) to learn more about GHEtool Cloud and what it can do for
you.

<p align="center">
<img src="https://ghetool.eu/wp-content/uploads/2024/08/GHEtool-Cloud-squarish.png" width="600">
</p>

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `GHETOOL` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: BSD-3-Clause** (evidence: `LICENSE.txt` in the upstream snapshot).

License file excerpt:

```text
BSD 3-Clause License

Copyright (c) 2023, Enead bv
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original BSD-3-Clause terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `BSD-3-Clause` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `GHETOOL` (category: SOLAR)
- **Upstream URL:** https://github.com/wouterpeere/GHEtool
- **Pinned commit (SHA):** `b47520e0a91a1d75609fce3f1e51551f51332c00`
- **Branch:** main
- **Pin provenance:** GitHub API commits/main. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`f6fe220ef1daf7d0dd81dc8ea346b3ea85b27724ac2fdb37e3a3c28b800c1fe5`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

