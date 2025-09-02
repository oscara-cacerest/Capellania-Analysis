# NDVI Algorithm – Prediction and Land Cover Classification in the Capellanía Wetland (Bogotá)

This repository contains a Python algorithm developed for the analysis and projection of vegetation cover in the **Capellanía Wetland in Bogotá, Colombia**.

The code processes spectral indices derived from satellite imagery (NDVI, NDWI, NDMI, MNDWI), trains a **Random Forest** model, and generates vegetation cover predictions for future dates, aiming to support ecosystem monitoring and environmental management.

The project is implemented in a **Jupyter notebook (.ipynb)** and is designed to work with Landsat 8 data.

---

## Main Features

- Processing of spectral indices (NDVI, NDWI, NDMI, MNDWI).
- Organization of temporal series by polygon (`fid`).
- Training of a Random Forest Regressor model to estimate NDVI.
- Projection of indices to future dates using linear regression.
- Generation of outputs in **GeoTIFF** format:
  - Predicted NDVI
  - Water mask
  - Thematic land cover classification in 5 classes

---

## Repository Structure
├── ALGORITMO_NDVI_vf_2.ipynb # Main notebook with the code
├── README.md # Project documentation


---

## Environment Setup in Python

Before running the notebook, make sure you have **Python 3.8 or higher** installed.

Install the required libraries with the following commands:

```bash
pip install pandas
pip install numpy
pip install geopandas
pip install scikit-learn
pip install rasterio
```

##  Usage

Adjust the input file paths in the notebook:

Excel file with spectral indices (INDICES_ESPECTRALES.xlsx).

Vector grid layer (CUADRICULA_RECORTE.gpkg).

Reference raster (.tif).

Define the target prediction date (YYYY-MM-DD).

Run the notebook, and the results will be saved in a folder RASTERS/pred_YYYY containing:

NDVI_pred_YYYY.tif

WATER_MASK_YYYY.tif

LANDCOVER_YYYY.tif

##  Example Output

The final classification is delivered in raster format with the following categories:

Code	Class
1	Water
2	Bare soil / No vegetation
3	Sparse vegetation
4	Moderate vegetation
5	Dense vegetation
0	No data
Project Context

The Capellanía Wetland, located in Bogotá, has undergone significant transformation due to urban growth and human pressures. This algorithm seeks to contribute to the monitoring of vegetation dynamics and the analysis of future scenarios, supporting decision-making in environmental management and conservation.

##  Recommendations

The notebook already contains the paths to the input files (Excel, GeoPackage, Raster).

To reproduce the algorithm in another environment, you must save the data files on your computer and update the paths in the notebook.

It is recommended to keep the same folder structure or create a dedicated working folder (e.g., D:/LANDSAT/).

The results are automatically generated in an output folder named with the prediction year (RASTERS/pred_YYYY).

##  License

This code is for academic use and may be reused with proper citation of the author.
