# AHRSMM_V1.0
Adaptive High-Resolution Soil Moisture Map (AHRSMM) Version 1.0

To map daily surface soil moisture at any location in the continental USA, with any spatial resolution and on any date since 2016/01/01, please do the following:

Please download all the 20 zip files and unzip them into one folder. Before you run the following R code, make sure you have the latest version of RTools (https://cran.r-project.org/bin/windows/Rtools/) and miniconda (https://docs.conda.io/en/latest/miniconda.html) or anaconda (https://www.anaconda.com/products/individual) installed.

If you have trouble installing "rgee" or activate it using "ee_Initialize()", please refer to here: https://r-spatial.github.io/rgee/articles/setup.html

Open the "AHRSMM_V1.0.R" file to start the mapping. Load the ".RData" which contains the fitted machine learning models and downloaded covariates for the sample Wisconsin field. You can also choose to refit the models yourself but it may take a longer time.

Generate a shapefile for the study field (region of interest, ROI) and load it to the R environment. Define the spatial resolution and the starting and ending dates you want to generate a surface soil moisture map.

Download the covariates from the Google Earth Engine and Google Cloud Storage using the R code. You need to create a Google Earth Engine account and initialize it using the R code.

Run the fitted machine learning model (now a Random Forest model, can be changed to others using the "caret:train" function) and predict soil moisture onto the region of interest defined by the shapefile.

If you have in situ soil moisture probe data, prepare them in a .csv file format using the template "Huges_VWC.csv". Then load your in situ measurements to the R environment and refit the model using the R codes. After that, apply the updated model to the ROI and generate the new soil moisture map. This is the "Adaptive" feature of the High-Resolution Soil Moisture Map. After you include local in situ data, the model will have an improved performacne at your own fields. Note: your input data is only accesible by yourself and will not be available to others.

If you have trouble using the R code or if you are interested in the collaboration on further improving this model, please feel free to send an email to Jingyi Huang (jhuang426@wisc.edu).

