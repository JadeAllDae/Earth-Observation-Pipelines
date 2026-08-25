# 🌍 Earth Observation Pipelines

A growing portfolio of cloud-native Python workflows and spatial pipelines dedicated to marine biogeochemistry, coastal monitoring, and high-performance Earth Observation (EO) analysis. 

This repository serves as a practical sandbox for processing multi-sensor satellite imagery and oceanographic data using modern, scalable data engineering practices (e.g., STAC, lazy-loading, and distributed computing).

---

## 📂 Current Pipelines

### 1. [Sentinel-2 STAC Temporal Median Composites](./01_STAC_Temporal_Median_Composites.ipynb)
**Objective:** Generate pristine, cloud-free, and atmospherically corrected imagery of dynamic coastal environments (Lady Elliot Island, Great Barrier Reef).
*   **The Problem:** Raw optical imagery of marine environments is heavily impacted by transient cloud cover, cloud shadows, and atmospheric haze.
*   **The Solution:** This pipeline queries the Microsoft Planetary Computer STAC API. It uses `xarray` and `dask` to lazily load time-series data and compute a mathematical temporal median pixel-by-pixel, effectively filtering atmospheric noise.
*   **Key Libraries:** `pystac-client`, `odc-stac`, `xarray`, `dask`, `matplotlib`

### 2. [Autonomous Ocean Robotics: 4D Argo Profiling](./02_Argo_Float_Vertical_Profiles.ipynb)
**Objective:** Query the global database of autonomous Argo profiling floats to extract and visualize 4D oceanographic profiles (Temperature and Salinity vs. Depth) across Western Australia.
*   **The Problem:** Traditional ocean sampling requires expensive research vessels, leaving massive spatial gaps in remote marine environments.
*   **The Solution:** This pipeline uses the `argopy` library to query the live Argo database via API. It converts the 4D data cube into vertical profiles, bridging the gap between physical in-situ robotics and spatial data structures.
*   **Key Libraries:** `argopy`, `xarray`, `pandas`, `matplotlib`

### 3. [Unsupervised ML: Coastline Extraction](./03_ML_Coastline_Extraction.ipynb)
**Objective:** Deploy machine learning to automatically extract coastal boundaries and track estuarine phase-shifts at Boambee Creek, NSW.
*   **The Problem:** Manually digitising coastlines for vulnerability assessments is inefficient and biased.
*   **The Solution:** This pipeline calculates MNDWI from Sentinel-2 data and applies Otsu’s Thresholding to automatically classify pixels into land vs. water without human input.
*   **Key Libraries:** `scikit-image`, `xarray`, `odc-stac`

### [4. Direct Cloud Access: Sentinel-3 Multidimensional NetCDF Cubes](04_Sentinel3_NetCDF_Cloud_Access.ipynb)
* **Objective:** Demonstrate direct cloud-filesystem access to complex multidimensional NetCDF data cubes, bypassing local downloads.
* **The Problem:** Advanced oceanographic sensors like Sentinel-3 store data in complex, multi-layered NetCDF formats that traditional loaders struggle to parse without downloading massive global swaths locally.
* **The Solution:** This pipeline uses Python's native cloud-filesystem reader (`fsspec`) and `xarray` to directly open and manipulate multidimensional data cubes straight from the Microsoft Planetary Computer, unpacking 32-bit Water Quality and Science Flags (WQSF).
* **Key Libraries:** `xarray`, `fsspec`, `pystac-client`, `h5netcdf`

---

## 🛠️ Core Tech Stack

This repository highlights the transition from traditional, local GIS processing to modern, cloud-native spatial frameworks:
*   **Data Discovery:** SpatioTemporal Asset Catalog (STAC) API
*   **Cloud Platforms:** Microsoft Planetary Computer, Google Earth Engine (GEE)
*   **Data Cubes & Parallel Computing:** `xarray`, `dask`, `netCDF4`
*   **Geospatial & Oceanographic Processing:** `geopandas`, `rasterio`, `odc-stac`, `argopy`

---

## 🚀 How to Run Locally

These pipelines are designed to be entirely reproducible. You do not need a paid cloud account or API keys to run the public scripts. To prevent dependency conflicts, please use the provided Conda environment blueprint.

1. **Clone this repository:**
   ```bash
   git clone [https://github.com/JadeAllDae/Earth-Observation-Pipelines.git](https://github.com/JadeAllDae/Earth-Observation-Pipelines.git)
   cd Earth-Observation-Pipelines

## 📫 About the Author

**Jade Farrugia**  
*PhD Candidate (Marine Biogeochemical Modelling) @ UWA*  
*Founder @ The Oceans Need Us*

I specialize in fusing Earth Observation data, autonomous marine robotics, and high-performance supercomputing to map coastal carbon export and ecosystem dynamics. 

To learn more about my research, my open-source work or The Oceans Need Us, please check out my main profile or connect with me below:

* 🐙 **Main GitHub Profile:** [JadeAllDae](https://github.com/JadeAllDae)
* 💼 **LinkedIn:** [jadefarrugia](https://www.linkedin.com/in/jadefarrugia)
* 🎓 **Google Scholar:** [Jade Farrugia](https://scholar.google.com/citations?user=NRfOnhkAAAAJ&hl=en&oi=ao)
* 🆔 **ORCID:** [0009-0003-5824-3603](https://orcid.org/0009-0003-5824-3603)
* 🌊 **NFP / Foundation:** [The Oceans Need Us](https://www.theoceansneedus.org)
