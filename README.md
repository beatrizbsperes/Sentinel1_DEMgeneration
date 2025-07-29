# Sentinel-1 DEM generation script

This project implements Digital Elevation Model (DEM) generation from Sentinel-1 SAR data using ESA's SNAP toolbox Python interface (esa_snappy). The analysis focuses on comparing DEM quality across different land cover types and perpendicular baseline configurations.

## Project Overview

The script and notebook generate DEMs through SAR interferometry (InSAR) processing of Sentinel-1 data, with specific focus on:

- **Land Cover Comparison**: Analyzing DEM performance in densely vegetated areas (Costa Rica) versus bare soil areas (Cabo Verde)
- **Baseline Analysis**: Comparing short perpendicular baselines (~30m) with longer baselines (~150m) for optimal DEM generation

## Requirements

### Software Dependencies
- **ESA SNAP Desktop** (version 12.)
- **Python 3.7+**
- **esa_snappy** (SNAP Python API)
- all the required packages from the ```environment.yml``` file

### Installation
1. Install ESA SNAP Desktop from [ESA's official website](https://step.esa.int/main/download/snap-download/)
2. Configure esa_snappy following the [official guide](https://senbox.atlassian.net/wiki/spaces/SNAP/pages/50855941/Configure+Python+to+use+the+SNAP-Python+snappy+interface)
3. Install correct environment:
```bash
# Create conda environment from file
conda env create -f environment.yml

# Activate environment
conda activate sar_env
```

## Data Requirements

### Sentinel-1 Data
- **SLC (Single Look Complex)** products from Sentinel-1A/B/C
- **IW** aquisition beam mode 
- **Coverage areas**:
  - Costa Rica: Dense tropical vegetation
  - Cabo Verde: Arid/semi-arid bare soil regions

Under the ```_data``` you can store your input data. After, when you run the pipeline don't forget to update the name in which the raw data was stored.

### Baseline Requirements
- **Short baseline**: ~30m perpendicular baseline
- **Long baseline**: >150m perpendicular baseline