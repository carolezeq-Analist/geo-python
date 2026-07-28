# geo-python
# 🌍 STAC Datasets & LiDAR Analysis

> **Daily geospatial experiments** – exploring INPE's STAC catalog and advanced terrain/vegetation analysis from LiDAR point clouds.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![STAC](https://img.shields.io/badge/STAC-INPE-green.svg)](https://data.inpe.br/bdc/stac/v1/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

##  About

This repository documents my daily geospatial Python experiments. Each script explores a different dataset or analysis technique, building a solid foundation in remote sensing, terrain analysis, and LiDAR processing.

**Goal:** Demonstrate proficiency with:
-  **STAC API** (INPE Brazil)
-  **LiDAR Point Clouds** (laspy)
-  **Terrain Analysis** (DEM, slope, hillshade, curvature)
-  **Vegetation Analysis** (Canopy Height Models)
-  **Data Visualization** (2D/3D, matplotlib)

---

##  Datasets Explored

| Day | Dataset | Topic | Script |
|-----|---------|-------|--------|
| 01 | **Sentinel-2** (S2-16D-2) | EVI & NDVI vegetation indices | [Stac_Evi.ipynb](Stac_Evi.ipynb) |
| 02 | **Topodata** (SRTM) | Embrapa slope classes | [Stac_Topodata_EVI.ipynb](Stac_Topodata_EVI.ipynb) |
| 03 | **MDT 50cm** (Portugal) | Terrain analysis (hillshade, slope, curvature) | [mdt_teste.ipynb](mdt_teste.ipynb) |
| 04 | **LiDAR** (São João, PT) | DEM, slope, hillshade, curvature from point cloud | [slope_lidar.ipynb](slope_lidar.ipynb) |
| 05 | **LiDAR** (São João, PT) | Canopy Height Model (CHM) & vegetation analysis | [lidar_vegetation.ipynb](lidar_vegetation.ipynb) |

---

##  Features

### STAC Integration
-  Connection to INPE Brazil STAC catalog
-  Spatial filtering (bbox)
-  Temporal filtering (datetime)
-  Cloud cover filtering
-  Multi-collection exploration

### LiDAR Processing
-  LAZ/LAS reading with `laspy`
-  Classification filtering (Ground, Vegetation)
-  DEM generation via interpolation (`griddata`)
-  KDTree-based ground interpolation (CHM)
-  Outlier filtering

### Terrain Analysis
-  Hillshade (custom azimuth/altitude)
-  Slope (degrees)
-  Aspect
-  Curvature (Laplacian)
-  Statistical summaries

### Visualization
-  2D plots with colormaps
-  3D scatter plots
-  Histograms
-  Side-by-side comparisons

### Exports
-  GeoTIFF with CRS/metadata
-  16-bit PNG (Blender-ready)
-  PLY point cloud (3D software)
-  CSV tabular data
-  High-resolution plots

---

##  Tech Stack

| Library | Purpose |
|---------|---------|
| `pystac-client` | STAC API queries |
| `rasterio` | GeoTIFF I/O |
| `laspy` | LiDAR point cloud handling |
| `numpy` | Numerical computing |
| `scipy` | Interpolation, KDTree, gradients |
| `matplotlib` | 2D/3D visualization |
| `geopandas` | Vector data (future) |
| `Pillow` | 16-bit PNG exports |
| `plyfile` | PLY format export |
| `pandas` | Tabular data manipulation |

---

##  Sample Outputs

### Sentinel-2 EVI & NDVI
![EVI NDVI](evi_ndvi_lado_a_lado.png)

### Topodata - Embrapa Slope Classes
![Topodata](sc_declividade.png)

### MDT Terrain Analysis
![MDT](DTM_Hillshade.png)

### LiDAR Canopy Height Model
![CHM](2d_canopyheight.png)

---

##  Getting Started

### Prerequisites

```bash
pip install pystac-client rasterio laspy matplotlib numpy scipy pillow geopandas shapely pyproj plyfile pandas
