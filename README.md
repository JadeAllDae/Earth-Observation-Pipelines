# Earth-Observation-Pipelines
Cloud-native Earth Observation pipelines that will grow as research progresses.

# 🌍 Earth Observation Pipelines

A growing portfolio of cloud-native Python workflows and spatial pipelines dedicated to marine biogeochemistry, coastal monitoring, and high-performance Earth Observation (EO) analysis. 

This repository serves as a practical sandbox for processing multi-sensor satellite imagery and oceanographic data using modern, scalable data engineering practices (e.g., STAC, lazy-loading, and distributed computing).

---

## 📂 Current Pipelines

### 1. [Sentinel-2 STAC Temporal Median Composites](./01_STAC_Temporal_Median_Composites.ipynb)
**Objective:** Generate pristine, cloud-free, and atmospherically corrected imagery of dynamic coastal environments (Lady Elliot Island, Great Barrier Reef).
*   **The Problem:** Raw optical imagery of marine environments is heavily impacted by transient cloud cover, cloud shadows, and atmospheric haze.
*   **The Solution:** This pipeline queries the **Microsoft Planetary Computer STAC API** for months of Sentinel-2 L2A imagery. It uses `xarray` and `dask` to lazily load the time-series data and compute a mathematical temporal median pixel-by-pixel, effectively vaporizing clouds and filtering atmospheric noise.
*   **Key Libraries:** `pystac-client`, `odc-stac`, `xarray`, `dask`, `matplotlib`

*(More pipelines to be added as research progresses...)*

---

## 🛠️ Core Tech Stack

This repository highlights the transition from traditional, local GIS processing to modern, cloud-native spatial frameworks:
*   **Data Discovery:** SpatioTemporal Asset Catalog (STAC) API
*   **Cloud Platforms:** Microsoft Planetary Computer, Google Earth Engine (GEE)
*   **Data Cubes & Parallel Computing:** `xarray`, `dask`, `netCDF4`
*   **Geospatial Processing:** `geopandas`, `rasterio`, `odc-stac`

---

## 🚀 How to Run Locally

These notebooks are designed to be entirely reproducible. You do not need a paid cloud account or API keys to run the public data pipelines. 

1. Clone this repository:
   ```bash
   git clone [https://github.com/your-username/Earth-Observation-Pipelines.git](https://github.com/your-username/Earth-Observation-Pipelines.git)

   
