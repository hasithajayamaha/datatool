# datatool

## Overview

**datatool** is an HPC-independent workflow enabling users to extract subsets from community meteorological datasets through a simple command-line interface (CLI). It is designed to work primarily with NetCDF files, but is not limited to any specific file format, structure, or dataset. By leveraging crowdsourcing, datatool empowers community members to extract subsets from a wide range of available datasets.

## Features

- Extract subsets from large meteorological datasets
- Flexible support for various file formats (primarily NetCDF)
- Simple CLI for specifying datasets, variables, spatial/temporal bounds, and more
- Supports job submission to SLURM clusters and other HPC environments
- Extensible via community-contributed scripts and recipes

## Quick Start

The main entry point is the `extract-dataset.sh` script. Example usage:

```sh
./extract-dataset.sh [options...]
```

**Common options:**
- `-d, --dataset` : Meteorological forcing dataset of interest
- `-i, --dataset-dir=DIR` : Source path of the dataset file(s)
- `-v, --variable=var1[,var2[...]]` : Variables to process
- `-o, --output-dir=DIR` : Output directory for processed files
- `-s, --start-date=DATE` : Start date of the data
- `-e, --end-date=DATE` : End date of the data
- `-l, --lat-lims=REAL,REAL` : Latitude bounds (optional)
- `-n, --lon-lims=REAL,REAL` : Longitude bounds (optional)
- `-a, --shape-file=PATH` : Path to ESRI shapefile (optional)
- `-j, --submit-job` : Submit extraction as a job on SLURM (optional)
- `-C, --cluster=JSON` : JSON file with cluster-specific details
- `-L, --list-datasets` : List all available datasets and keywords
- `-V, --version` : Show version
- `-h, --help` : Show help and exit

For a full list of options, run:
```sh
./extract-dataset.sh --help
```

## Examples

Example scripts for subsetting datasets and job submission are available in the [examples/](examples/) directory. See `examples/README.md` for details.

## Directory Structure

- `extract-dataset.sh` — Main CLI script for data extraction
- `docs/` — Sphinx documentation (see [ReadTheDocs](https://datatool.readthedocs.io/en/latest/))
- `examples/` — Example scripts for various datasets and workflows
- `etc/` — Cluster and scheduler configurations, utility scripts
- `var/repos/builtin/recipes/` — Community-contributed dataset recipes and scripts
- `opt/`, `share/`, `var/` — Additional resources, licenses, and data
- `.readthedocs.yaml` — ReadTheDocs configuration
- `CHANGELOG`, `LICENSE`, `VERSION` — Project metadata

## Documentation

Full documentation is available at:  
[https://datatool.readthedocs.io/en/latest/](https://datatool.readthedocs.io/en/latest/)

## License

Meteorological Data Processing Workflow - datatool  
Copyright (C) 2022-2023, University of Saskatchewan  
Copyright (C) 2023-2025, University of Calgary  
Copyright (C) 2022-2025, datatool developers

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
