Title: El Nino-Southern Oscillation (ENSO) Prediction Using Neural Networks

Students: Lilian Zhu

Group: Anomaly Detection Aces

**Project Description:**
The El Nino-Southern Oscillation (ENSO) is an interannual cycle in the Pacific Ocean that happens every three to seven years, split into two phases: El Nino and La Nina. During El Nino, we experience a warm anomaly and decreased upwelling in the Eastern Pacific, as well as weakening of the easterly winds. During La Nina, we experience the opposite: cold anomalies, increased upwelling, and stronger easterlies. The NINO3.4 region is a region in the ocean that encompasses both El Nino and La Nina phases. The Oceanic Nino Index (ONI) is a three month rolling mean of sea surface temperature anomaly averaged across NINO3.4. These two phases are quantified in the following way:

ONI > 0.5 : El Nino and ONI < 0.5 : La Nina

Understanding ENSO and accurately predicting these phases are critical to knowing temperature and precipitation trends on Earth. These phases have global impacts beyond the tropical Pacific, and can affect economies across the globe. Therefore, we propose a convolutional neural network to predict the cycles of ENSO with the following input and output:

**Set up and run instructions** 
Input: We use sea surface temperature (SST) with time lags of 3 months up to two years as our channels to the CNN
Output: ONI

And the following Training/Validation/Testing structure:

Training and Validation: Data will come from the Community Earth System Model (CESM) which is an ensemble of 40 climate models from all around the world. We will use a total of 10 ensembles from CESM: 9 for training and 1 for validation

Testing: We test our model on ERA5, a reanalysis climate product which is often used as a proxy for observations

**Instructions:**
Because Google Collab has a restricted enviornment, I am unable to import the data via HTTPS/SSL which is the only way the data can be accessed. 

This is the code I ran to get the data on my machine, and then I downlaoded it locally and uploaded it to Google Drive to be used in Google Colab.

```
url = "https://climatedata.ibs.re.kr:9443/dods/public-data/cesm2-lens/ocn/TEMP/cesm2-lens-TEMP.1850-2100.mon.1x1"
ds = xr.open_dataset(url)
print(ds)
```

The CESM data description used for training and validation is [here](https://www.cesm.ucar.edu/community-projects/lens2).

To obtain ERA5 data, you must request the data based on the following parameters on [this](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels?tab=download) website.

Product type: Reanalysis
Variable: sea surface temperature
Years: 1980 to 2020
Months: Select all
Day: Select all
Time: Select all
Geographical area: Whole available region
Data format: NetCDF4
Download format: Unarchived

Similar to the CESM data, I downloaded it and uploaded it to be used in this Google Colab notebook.

How to run the code:
After successfully downloading the data, add the Google Drive folder with the data to your personal drive. Then when you mount google drive, the file path should go directly to the data as desired.


Make sure to download all the listed python packages. The code should run successfully.
requirements.txt lists all python packages and their versions.



