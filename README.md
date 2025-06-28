# GIS

2015 
https://code.earthengine.google.com/15c0418000e148edc82c8090817fb91e

2020
https://code.earthengine.google.com/dcc4c66c239c88b18de137875d2b0248

# 🌍 Dynamic Soil Erosion Risk Mapping using Remote Sensing and Google Earth Engine

This project focuses on generating **spatially precise soil erosion risk maps** using multi-source satellite data and machine learning-based land cover classification. It integrates **terrain, climate, and vegetation factors** to derive actionable insights for sustainable land management.

---

## 🔧 Project Objective

To compute and visualize **dynamic soil erosion risk** across a selected study area by:
- Using satellite-derived **NDVI**, **slope**, and **precipitation** as key inputs
- Performing **land cover classification** using Random Forest and SVM
- Identifying vulnerable zones and generating **interpretable risk maps** for environmental decision-making

---

## 🛰️ Datasets Used

| Dataset | Source | Purpose |
|--------|--------|---------|
| **Landsat 8** (`LANDSAT/LC08/C02/T1_L2`) | USGS/NASA | NDVI, NDWI, NDBI, base imagery |
| **SRTM DEM** (`USGS/SRTMGL1_003`) | NASA | Elevation data for calculating **slope** |
| **CHIRPS Precipitation** (`UCSB-CHG/CHIRPS/DAILY`) | UCSB Climate Hazards Group | Rainfall data (annual total) |
| **Custom Polygons** | User-defined | Ground truth training regions |

---

## 📌 Key Methodology

### 🔹 Land Cover Classification
- Manually digitized polygons for five classes:
  - Densely Forested
  - Sparsely Forested
  - Deforested
  - Built-up (Urban)
  - Riverbank
- Trained **Random Forest Classifier (RFC)** and **Support Vector Machine (SVM)**
- Evaluated model using **confusion matrix** and **overall accuracy** (achieved ~92%)

### 🔹 Soil Erosion Risk Formula
```text
Erosion Risk = Normalized Slope × (1 - Normalized NDVI) × Normalized Precipitation
