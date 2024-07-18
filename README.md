# CAS-Clumping-Index-Products
The canopy clumping index (CI) is a measurement of the spatial distribution pattern of foliage. Foliage commonly has a non-random distribution, which is aggregated at the canopy, branch, and shoot scales. Theoretically, CI is >0. When CI < 1, the foliage has a clumping distribution. When CI > 1, the foliage has a regular distribution. The foliage has a random distribution when CI = 1. This software, programmed by JavaScript based on Google Earth Engine (GEE), is to produce global CI products using the MODIS dataset. It is a visualization software that runs directly in the GEE to provide CI downloading at a user-defined scale.


Now, CI products are released in TIFF format from March 1, 2000, to May 1, 2020, at regional or global scales, with temporal scales ranging from daily to monthly and yearly. Publications referring to the methods and technologies used are listed at the end of this page. The program mainly consists of the following steps:

Filter image datasets by the designated date range to obtain the desired image collections.
Generate a multi-band image containing the required data and stack it in an image collection for CI retrieval.
Retrieve daily CI based on band calculations and exclude low-quality pixels.
Apply the Savitzky-Golay smoothing filter (SG-filter) to the daily CI collection, then composite a monthly or yearly CI image by quality indicator, and provide the final CI for download.


The descriptions of software usage are as follows: 

The initialized interface includes a date slider at the top of the map, which provides a quick daily CI view

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/startedInterface.jpg" width='500px'>

1) Input the start and end dates, then click on one of the temporal scales. The desired product options will be returned.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/inputdate.jpg" width='500px'>

2) Select one of the date to get the product.

<p float="left">
<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/daily.jpg" height='300px' width='200px'/> <img         src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/monthly.jpg" height='300px' width='200px'/> <img         src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/yearly.jpg" height='300px' width='200px'/>
</p>

3) You can select the spatial scale to export or view the product, and then new final buttons will appear.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/dailyImg.jpg" width="500px">

4) After clicking 'View,' the corresponding image named by its date will be added to the map.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/loadLayer.jpg" width="500px">

5) Due to constraints by GEE, exporting the global extent (60°S–90°N, 180°E–180°W) product will automatically clip it into nine equal-sized pieces. You can set the file name and save folder.

<p float="left">
<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/export.jpg" width="500px"> <img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/exportSettings.jpg" width="500px">
</p>
 
6) After selecting 'draw a rectangle to export or view,' you can draw one or several rectangles and select one to view or download. The small regional image can be downloaded as a single image file to your Google Drive.

<img src="https://github.com/CUGLiving/Clumping-Index-Products/blob/main/softwareShots/regionalExport.jpg" width="500px">

All input datasets are provided by the GEE Data Catalog except for a fraction of vegetation coverage (FCOVER) and global land cover data. The land cover image is a single-year product, and the FCOVER is a monthly product. We have uploaded the FCOVER up to May 2020. Future FCOVER data will be uploaded once the latest product is available. The land cover product can be acquired at http://bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php and the FCOVER data at https://land.copernicus.vgt.vito.be/PDF/portal/Application.html#Home.

The products from March 2000 to May 2020 are currently available for download. Fortunately, you can still download products outside this date range because the program is designed to automatically use the nearest date-adjacent FCOVER data.


There are several instructions, as follows:

1) Please type the dates formatted as "2020-01-01".
2) The exported CI band has been scaled 1000 times.
3) You will see nine pieces of the image in your Google Drive after you export the global image.
4) All products named by their date include two bands (CI band and Quality band); more information about the products can be found at the end of this page.
5) The default name for the exported folder is "CIFolder," which you can modify as you like.
6) The fast-open link to this program is https://code.earthengine.google.com/?scriptPath=users%2Flrvings%2FGMap%3AClumpingIndex%2FCAS-CI.


References:

[1] Li, Y., and H. Fang (2022). "Real-Time Software for the Efficient Generation of the Clumping Index and Its Application Based on the Google Earth Engine" Remote Sensing 14(15): 3837. https://doi.org/10.3390/rs14153837.

[2] Wei, S., H. Fang, C. B. Schaaf, L. He, and J. M. Chen (2019). "Global 500 m clumping index product derived from MODIS BRDF data (2001–2017)." Remote Sensing of Environment 232: 111296. https://doi.org/10.1016/j.rse.2019.111296.

[3] Wei, S.; Fang, H. Estimation of canopy clumping index from MISR and MODIS sensors using the normalized difference hotspot and darkspot (NDHD) method: The influence of BRDF models and solar zenith angle Remote Sens. Environ. 2016, 187, 476–491. https://doi.org/10.1016/j.rse.2016.10.039
