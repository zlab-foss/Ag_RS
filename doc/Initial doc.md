###### This is the 2nd version of doc, which is going to be improved...

### Codes have to be compiled in the following manner:

### 1. Initial_preparation.ipynb

# This code is mainly related to the import of necessary  libraries. In the first step, Google Earth Engine and Google colab authentication procedures are conducted.
# The, the user draws his/ her polygon of interest (mainly a specific cropland).
# Dran polygon is going to be used in other parts.

### 2. Data_Preparation.ipynb

# In this part, we are preparing remote ensing satellite imageries (Sentinel-2 data) to be used in the upcoming codes.
# First, there is a function, in which cloud-free images over the imported polygon (last code) are clipped and returned to the front section.
# Images are also downloaded and saved in Google Shahred Drives to be used.


### 3. Indices_Computation.ipynb

# From the saved images, in this part different well-known vegetation indices are computed.
# Indices are: 
1-NDVI
2-NDRE1 
3-NDRE2 
4-NDRE3 
5-MSAVI 
6-CCCI 
7- NDWI
# These indices are computed based on mathematical formaulas which can be found in articles.

### 4.LAI_computation.ipynb

# LAI needs to be computed by supervised models. We have first trained a model (XGboost regression model) to compute LAI from image bands.
# This code uses bands of the stored images (See Data_Preparation.ipynb) and the trained model to compute LAI index.
# trained model is also provided in 'doc' folder.

### 5.Anomaly detection.ipynb

# In this part, anomalies are found in the drwan polygon of user.  Anomaly is defined as the distinct region in the image, compared to background (main parts)
# Input is the stacked of codes 3 and 4 (Indices_Computation, LAI_computation)
# Anomalies are detected using RX anomaly detection algorithm or one-class SVM.
# Detected anomalies might be related to positively or negatively grown products, which are detected using 2-cluster K-means algorithm.


