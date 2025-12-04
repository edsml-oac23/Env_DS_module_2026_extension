# Environmental Data Science Module Modernization Plan

## Week 1: Climate Data & Time Series Analysis
*Focus: Handling multidimensional climate data (NetCDF), time-series statistics, and spatial interpolation.*

| Current Content (ESE-ADA) | Brief Explanation | Modernized Proposal (OpenGeos/AI) |
| :--- | :--- | :--- |
| **1. Climate Modelling & Data Access** | Introduction to climate model physics and manual retrieval of NetCDF files from Dropbox/archives. | **Automated Ingestion (`geoai.download`):** Use `geoai` to programmatically fetch climate/weather rasters from STAC APIs (e.g., Planetary Computer) instead of manual downloads. |
| **2. Time-Series Analysis** | Statistical analysis of temporal data (trends, seasonality) using standard libraries (likely `pandas`/`statsmodels`). | **AI-Driven Forecasting:** Introduce `geoai` or `torchgeo` for time-series forecasting using LSTMs or Transformers on climate data stacks. |
| **3. Geostatistics (Kriging)** | Spatial interpolation methods to estimate values between sampled points (e.g., rainfall stations). | **Spatial ML Interpolation:** Use Random Forest or Gaussian Processes via `scikit-learn` (integrated in `geoai` workflows) which often outperform traditional Kriging. |
| **4. Practical: 'Winery Project'** | A capstone analysis combining climate suitability and soil data for a specific vineyard location. | **Precision Ag with GeoAI:** Use `samgeo` (Segment Anything) to automatically delineate vine rows from satellite imagery and overlay dynamic climate data fetched via `geoai`. |

## Week 3: Remote Sensing & Spatial Analysis
*Focus: Earth Observation physics, raster processing, and image classification.*

| Current Content (ESE-ADA) | Brief Explanation | Modernized Proposal (OpenGeos/AI) |
| :--- | :--- | :--- |
| **1. Remote Sensing Physics** | Fundamentals of electromagnetic spectrum, sensor resolution, and physics of optical/radar sensors. | **Foundation Models Concept:** Add a module on how Large Vision Models (like SAM/DINO) "see" the spectrum differently than traditional pixel-based physics models. |
| **2. Raster Operations & PCA** | Basic algebra on raster pixels (NDVI calculation) and Principal Component Analysis for dimensionality reduction. | **Interactive Processing (`leafmap`):** Use `leafmap` to calculate spectral indices (NDVI) on-the-fly and visualize PCA results interactively on web maps. |
| **3. Classification (RF/K-Means)** | Supervised (Random Forest) and Unsupervised (K-Means) classification for land cover mapping. | **Deep Learning (`geoai.train`):** Replace RF with **U-Net** or **DeepLabV3+** training using `geoai.train_segmentation_model` for state-of-the-art accuracy. |
| **4. Data Access (Manual)** | Instructions to download Sentinel-2/Landsat data via Dropbox or GEE Code Editor. | **STAC API (`geoai.download`):** Script the download of Sentinel-2 imagery using `download_pc_stac_item` to create reproducible data pipelines. |
| **5. Practical: 'Nagazaki'** | A mini-project likely focusing on change detection or urban mapping using traditional classifiers. | **Zero-Shot Detection (`samgeo`):** Use **SAM (Segment Anything)** to automatically detect buildings or damage without training a model. Use **Text Prompts** (e.g., "damaged building") with `LangSAM`. |
| **6. Terrain & LiDAR** | Analyzing elevation models (DEMs) and LiDAR point clouds. | **3D Visualization (`leafmap`):** Use `leafmap` to visualize LiDAR point clouds directly in the notebook and overlay segmentation masks from `samgeo` on 3D terrain. |