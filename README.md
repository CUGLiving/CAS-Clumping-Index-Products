# CAS-Clumping-Index-Products
The canopy clumping index (CI) is a measurement of the spatial distribution pattern of foliage. Foliage commonly has a non-random distribution, which is aggregated at the canopy, branch, and shoot scales. Theoretically, CI is >0. When CI < 1, the foliage has a clumping distribution. When CI > 1, the foliage has a regular distribution. The foliage has a random distribution when CI = 1. This software programmed by JavaScript based on Goole Earth Engine （GEE） is to produce global CI products using MODIS dataset. It is a visualization software which runs directly in the GEE to provide CI downloading at a user-defined scale.


Now, CI products are released by tif format from March 1, 2000 to May 1, 2020, at regional or global scale, with a temporal scale ranges from daily, montly, and yearly. Publications to which methods and technologies were referred are listed at the end of this page. The program is mainly composed of the following steps:

1) filter image datasets by designated date range to corresponding image collections.
2) generate multi-band image containing the required data and stack it in a image collection for CI retrieval.
3) Retrieve daily CI based on band calculations and exclude low quality pixels.
4) The Savitzky-Golay smoothing filter (SG-filter) was conducted for daily CI collection then to composite monthly or yearly CI image by quality indicator and provide final CI to download.

The descriptions of software usage:

the initialized interface, the dateslider in the top of the map provides a daily CI quick view

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/startedInterface.jpg" width='500px'>

1)After two dates input and click one of temporal scales, the desired products options will appear.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/inputdate.jpg" width='500px'>

2)select one of date point to get product.

<p float="left">
<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/daily.jpg" height='300px' width='200px'/><img         src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/monthly.jpg" height='300px' width='200px'/><img         src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/yearly.jpg" height='300px' width='200px'/>
</p>

3)You can select spatial scale to export or view product, then the new final buttons will appear.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/dailyImg.jpg" width="500px">

4)The corresponding image named by its date will be added to the map after click view.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/loadLayer.jpg" width="500px">

5)Because of constraints by GEE, exporting the global extent (60°S-90°N,180°E-180°W) product will be automatically clipped into 9 equal-sized pieces of image. You can set the file name and saved folder.

<p float="left">
<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/export.jpg" width="500px"><img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/exportSettings.jpg" width="500px">
</p>
 
6)After select "draw a rectangle to export/view", you can draw one or several rectangles and select one of them to view or download. The small regional image can be downloaded to one image file in your Goole Drive. 

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/regionalExport.jpg" width="500px">

Notes:
All input datasets are provided by GEE Data Catalog expecting fraction of vegetation coverage (FCOVER) and Global land cover. The land cover image is a single year product, and the FCOVER is the monthly product, we currently have been uploading the FCOVER to May 2020. The following FCOVER will be contiguously uploaded once it latest one is available. The land cover product is available from http://bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php and the FCOVER is from https://land.copernicus.vgt.vito.be/PDF/portal/Application.html#Home.

The products from 2000-03 to 2020-05 are currently for downloading, but you can still download products not confind this date range because the program is designed to automaticallly take the date-adjacent FCover to produce. 

There are several instructions as follow:
 1) please type date formatted as "2020-01-01".
 2) The exported CI band has been scaled 1000 times.
 3) You will see 9 pieces of image in your google derive after you exported the global image.
 4) All products named by its date includ 2 bands (CI band and Quality band), more information about products can see the reference in the end of this page;
 5) I give a name of exported folder ("CIFolder"), you can modify as you like.
 6) The fast open link of this program see "https://code.earthengine.google.com/?scriptPath=users%2Flrvings%2FGMap%3AClumpingIndex%2FCAS-CI".


References:

[1] Li, Y. and H. Fang (2022). "Real-Time Software for the Efficient Generation of the Clumping Index and Its Application Based on the Google Earth Engine." Remote Sensing 14(15): 3837. https://doi.org/10.3390/rs14153837.

[2] Wei, S., H. Fang, C. B. Schaaf, L. He and J. M. Chen (2019). "Global 500 m clumping index product derived from MODIS BRDF data (2001–2017)." Remote Sensing of Environment 232: 111296.https://doi.org/10.1016/j.rse.2019.111296.

[3] Wei, S.; Fang, H. Estimation of canopy clumping index from MISR and MODIS sensors using the normalized difference hotspot and darkspot (NDHD) method: The influence of BRDF models and solar zenith angle. Remote Sens. Environ. 2016, 187, 476–491.https://doi.org/10.1016/j.rse.2016.10.039
