# Environmental Data Science Module Modernization Plan

---

## Week 1: Climate Data & Time Series Analysis
*Focus: Handling multidimensional climate data (NetCDF), time-series statistics, and spatial interpolation.*

| **Current Content (ESE-ADA)** | **Brief Explanation of Current Aim** | **Modernized Proposal (OpenGeos/AI)** |
| :--- | :--- | :--- |
| **1. Climate Modelling & Data Access** | Introduces climate model physics, scenarios, and manual access to climate datasets from static archives. <br>**Weak:** Manual retrieval; non-reproducible workflows; no scalable access pipeline. | **Automated Climate Ingestion:** Use STAC APIs (Planetary Computer, NASA CMR) with programmatic querying for climate and weather cubes. Build reproducible pipelines using `pystac_client` and integrate with `xarray` for automated loading. |
| **2. Time-Series Analysis** | Covers trends, seasonality, anomalies, and temporal statistics using Pandas and StatsModels. <br>**Weak:** Limited to 1D series; no multidimensional climate cubes; no AI-based forecasting. | **Multidimensional Time-Series:** Process labelled climate cubes with `xarray` and `rioxarray`. Introduce LSTM/Transformer forecasting for climate anomalies and spatio-temporal patterns. |
| **3. Geostatistics (Kriging, IDW)** | Teaches classical interpolation techniques (Kriging, IDW) for estimating climate variables between station points. <br>**Weak:** Traditional-only methods; no ML interpolation; limited uncertainty quantification. | **Spatial ML Interpolation:** Combine spatial ML (Random Forest, Gaussian Processes) with geospatial data workflows. Produce uncertainty surfaces, cross-validated error maps, and hybrid ML–geostatistical approaches. |
| **4. Practical: “Winery Project”** | A practical exploring vineyard suitability using static climate and soil layers and geostatistical interpolation. <br>**Weak:** Static datasets; manual workflows; no EO integration; no automation. | **“Smart Vineyard” with GeoAI:** Detect vine rows using `samgeo` from high-resolution imagery. Overlay climate anomalies, rainfall, NDVI trends, and soil layers. Build an interactive suitability dashboard using `leafmap` and automated climate ingestion. |

---

## Week 3: Remote Sensing & Spatial Analysis
*Focus: Earth Observation physics, raster processing, PCA, indices, and environmental classification.*

| **Current Content (ESE-ADA)** | **Brief Explanation of Current Aim** | **Modernized Proposal (OpenGeos/AI)** |
| :--- | :--- | :--- |
| **1. Remote Sensing Physics** | Introduces spectral bands, sensor characteristics, and radiometric principles. <br>**Weak:** Pixel-centric; lacks modern representation learning concepts. | **Foundation Model Awareness:** Explain how large vision models (SAM, DINOv2, CLIP) extract semantic structure, enabling advanced EO workflows beyond raw pixel interpretation. |
| **2. Raster Operations & Spectral Indices** | Teaches NDVI calculations, spectral algebra, and PCA using static scripts. <br>**Weak:** Non-interactive plots; inefficient spectral stack processing. | **Interactive Raster Analysis:** Use `leafmap` for live NDVI/PCA visualization. Process full spectral stacks with `xarray` and `rioxarray`. Enable dynamic thresholding and band inspection on interactive maps. |
| **3. Classification (RF & K-Means)** | Introduces traditional ML techniques for land cover mapping. <br>**Weak:** No deep learning segmentation; no zero-shot abilities; limited performance on complex surfaces. | **Zero-Shot + DL Segmentation:** Use SAM and LangSAM for zero-shot segmentation (e.g., “find trees”, “find buildings”). Add U-Net and DeepLabV3+ segmentation via `geoai.train` for high-accuracy land cover inference. |
| **4. Terrain & LiDAR** | Covers DEM derivatives (slope, aspect) and basic LiDAR operations. <br>**Weak:** No 3D visualisation; limited hydrology; no LiDAR segmentation. | **3D Environmental Modelling:** Use `whiteboxtools` for terrain hydrology (flow accumulation, watershed). Visualize LiDAR point clouds in 3D with `leafmap`. Apply SAM to LiDAR-derived intensity rasters for vegetation/structure segmentation. |
| **5. Mini-Project: “Nagasaki Project”** | Remote sensing and spatial analysis project applying Week 3 concepts for urban/change analysis. <br>**Weak:** Traditional classification; manual before/after comparison; little automation. | **Automated GeoAI Change Detection:** Compute spectral change cubes with `xarray`. Use split-map comparison in `leafmap` for pre/post imagery. Extract building footprints with SAM to quantify change or damage automatically. |

---

## Cross-Module Modernization Themes

| **Theme** | **Modernization Goal** |
| :--- | :--- |
| **Reproducible Data Pipelines** | Move from manual downloads to fully automated STAC-based ingestion for climate and EO datasets. |
| **OpenGeos Integration** | Standardize workflows around `geoai`, `samgeo`, `leafmap`, `geopandas`, `xarray`, `rioxarray`. |
| **Interactive Learning** | Use interactive maps and widgets to replace static figures across all notebooks. |
| **Spatial ML & GeoAI** | Introduce deep segmentation models, zero-shot methods, and modern vision foundation models in EO analysis. |
| **3D Environmental Analysis** | Extend DEM and LiDAR analysis to include terrain hydrology, 3D visualization, and structure/vegetation segmentation. |

---
