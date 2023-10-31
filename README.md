# CAS-Clumping-Index-Products
The canopy clumping index (CI) is a measurement of the spatial distribution pattern of foliage. Foliage commonly has a non-random distribution, which is aggregated at the canopy, branch, and shoot scales. Theoretically, CI is >0. When CI < 1, the foliage has a clumping distribution. When CI > 1, the foliage has a regular distribution. The foliage has a random distribution when CI = 1. This software, programmed by JavaScript based on Google Earth Engine (GEE), is to produce global CI products using the MODIS dataset. It is a visualization software that runs directly in the GEE to provide CI downloading at a user-defined scale.


Now, CI products are released in tif format from March 1, 2000, to May 1, 2020, at a regional or global scale, with a temporal scale ranging from daily, monthly, and yearly. Publications to which methods and technologies were referred are listed at the end of this page. The program is mainly composed of the following steps:

1) Filter image datasets by designated date range to corresponding image collections.
2) generate a multi-band image containing the required data and stack it in an image collection for CI retrieval.
3) Retrieve daily CI based on band calculations and exclude low-quality pixels.
4) The Savitzky-Golay smoothing filter (SG-filter) was conducted for daily CI collection, then to composite a monthly or yearly CI image by quality indicator and provide the final CI to download.

The descriptions of software usage are:

the initialized interface, the dateslider at the top of the map provides a daily CI quick view.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/startedInterface.jpg" width='500px'>

1) After two dates of input and clicking one of the temporal scales, the desired product options will appear.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/inputdate.jpg" width='500px'>

2) Select one of the date points to get the product.

<p float="left">
<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/daily.jpg" height='300px' width='200px'/> <img         src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/monthly.jpg" height='300px' width='200px'/> <img         src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/yearly.jpg" height='300px' width='200px'/>
</p>

3) You can select spatial scale to export or view the product, and then the new final buttons will appear.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/dailyImg.jpg" width="500px">

4) The corresponding image, named by its date, will be added to the map after clicking View.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/loadLayer.jpg" width="500px">

5) Because of constraints by GEE, exporting the global extent (60°S–90°N, 180°E-180°W) product will be automatically clipped into nine equal-sized pieces of image. You can set the file name and saved folder.

<p float="left">
<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/export.jpg" width="500px"> <img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/exportSettings.jpg" width="500px">
</p>
 
6) After selecting "draw a rectangle to export or view", you can draw one or several rectangles and select one of them to view or download. The small regional image can be downloaded to one image file in your Google Drive.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/regionalExport.jpg" width="500px">

Notes:
All input datasets are provided by the GEE Data Catalog, expecting a fraction of vegetation coverage (FCOVER) and global land cover. The land cover image is a single-year product, and the FCOVER is a monthly product. We are currently uploading the FCOVER to May 2020. The following FCOVER will be continuously uploaded once the latest one is available. The land cover product is available at http://bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php. and the FCOVER is from https://land.copernicus.vgt.vito.be/PDF/portal/Application.html#Home.

The products from 2000-03 to 2020-05 are currently available for downloading, but you can still download products outside of this date range because the program is designed to automatically take the date-adjacent FCover to produce.

There are several instructions, as follows:
1) Please type the date formatted as "2020-01-01".
2) The exported CI band has been scaled 1000 times.
3) You will see nine pieces of image in your Google Derive after you export the global image.
4) All products named by their date include 2 bands (CI band and Quality band); more information about products can be found at the end of this page.
5) I give the name of the exported folder ("CIFolder"), which you can modify as you like.
6) The fast-open link to this program is "https://code.earthengine.google.com/?scriptPath=users%2Flrvings%2FGMap%3AClumpingIndex%2FCAS-CI".


References:

[1] Li, Y., and H. Fang (2022). "Real-Time Software for the Efficient Generation of the Clumping Index and Its Application Based on the Google Earth Engine" Remote Sensing 14(15): 3837. https://doi.org/10.3390/rs14153837.

[2] Wei, S., H. Fang, C. B. Schaaf, L. He, and J. M. Chen (2019). "Global 500 m clumping index product derived from MODIS BRDF data (2001–2017)." Remote Sensing of Environment 232: 111296. https://doi.org/10.1016/j.rse.2019.111296.

[3] Wei, S.; Fang, H. Estimation of canopy clumping index from MISR and MODIS sensors using the normalized difference hotspot and darkspot (NDHD) method: The influence of BRDF models and solar zenith angle Remote Sens. Environ. 2016, 187, 476–491. https://doi.org/10.1016/j.rse.2016.10.039
