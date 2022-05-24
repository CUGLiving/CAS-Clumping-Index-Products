# CAS-Clumping-Index-Products
The Canopy CI (clumping index) indicates the spatial distribution pattern of foliage. CI=1: random distribution; CI>1: regular distribution; CI<1: clumping distribution. This program codeed by JavaScript in Goole Earth Engine （GEE） to produce global CI products based on the remote sensing dataset, it is a visualization software that runs directly in the GEE to provide CI products downloading with a self-defined scale.

Currently, users can directly get daily, montly, yearly CI image from March 2000 to May 2020 and can export in a global or regional scale.
All methods and technologies are referenced from the perivous puiblications on the end of this page. The main constitutes of the codes is:
1) filter image datasets by designated date range to into corresponding imagecollections.
2) generate multi-band image containing the required data and stack it in a image collection for CI retrieval.
3) Retrieve daily CI based on band calculations and exclude low quality pixels.
4) The Savitzky-Golay smoothing filter (SG-filter) was conducted for daily CI collection then to composite monthly or yearly CI image by quality indicator and provide final CI to download.


The description of software usage:
the initialized interface
<img src="https://user-images.githubusercontent.com/41323376/169938918-a286d66f-b651-4eca-bc07-a1583834fd62.jpg" width="800px">
1) After two dates input, the desired products options are appeared.
<img src="https://user-images.githubusercontent.com/41323376/169941305-725115e4-8fdb-4357-90de-e0e4d81d0053.jpg" width="800px">
2) select corresponding temporal scale to produce product
<img src="https://Clumping-Index-Products/softwareShots/daily.jpg)

3) You can select spatial scale to export or view product, then the new final buttons will appear
<img src="" width="800px">
4) The corresponding image named by its date will be added to the map after click export or view

5) the dateslider in the top of the map provides a daily CI quick view


Expecting fCover and specific Global land cover are required to upload manually, other all input data are provided by GEE Data Catalog.
The author assigned global land cover was download from http://bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php; I have uploaded it.
Under the retriction, The fCover input has not been available completely.

I will upload monthly fCover within 2010-2020, so the final products will be downloaded during this interval, but anyone can downloaded fCover at other date from "https://land.copernicus.vgt.vito.be/PDF/portal/Application.html#Home" then uploaded to your own GEE assets; this means you need do a minor mondifidation in this program to get your desired products;

After the corresponding data are already; all daily, monthly, yearly products can be downloaded from this code;

up to 2022-05-15, the fCover have been uploaded to 2020-05, so the CI products from 2000-01 to 2020-05 are available for download; The fFcoer images  will be continuously uploading,but you can still download products during not confind this range because the program is designed to automaticallly take the approximate fCover to produce. 


Notes: this code is designed to provide an interactive download tool; after you run this code in GEE, an UI page is appeared and you need type two dates (the start date and end date of products you want), then you can click to produce what products do you need and select to export a global or regional image to your Google derive;
Some instructions as following:
 1) please type date with a form likes "2020-01-01";
 2) The image value has been scaled 1000, please slow down you click speed in UI page because calculating CI is not a easy work;
 3) The global product will be divided to 9 single images to export because the same set in GEE, so do not be astonished when you see 9 pieces of Image in your google derive;
 4) All products include 2 bands (CI band and Quality band) and are named by its date, more information about products can see the reference in the end of this page;
 5) I give a name of exported folder ("CIFolder"), you can modify as you like;
 6) The fast open link "https://code.earthengine.google.com/?scriptPath=users%2Flrvings%2FGMap%3AClumpingIndex%2FUIClumpIndex";



[1] Wei, S. and H. Fang (2016). "Estimation of canopy clumping index from MISR and MODIS sensors using the normalized difference hotspot and darkspot (NDHD) method: The influence of BRDF models and solar zenith angle." Remote Sensing of Environment 187: 476-491.

[2] Wei, S., H. Fang, C. B. Schaaf, L. He and J. M. Chen (2019). "Global 500 m clumping index product derived from MODIS BRDF data (2001–2017)." Remote Sensing of Environment 232: 111296.
