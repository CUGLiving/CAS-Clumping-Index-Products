# Clumping-Index-Products
CI (clumping index) indicates the spatial distribution pattern of foliage. CI=1: random distribution; CI>1: regular distribution; CI<1: clumping distribution;
All methods and technologies are referenced from the puiblications in the end of this page;

Google Earth Engine JS code produce Clumping Index to download;
The program are designed to provide all products so long as the input data is already; 

Expecting fCover and specific Global land cover are required to upload manually, other all input data are provided by GEE Data Catalog.
The author assigned global land cover was download from http://bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php; I have uploaded it.
Under the retriction, The fCover input has not been available completely.

I intend to upload monthly fCover within 2002-2020, so the final products will be downloaded during this interval, but anyone can downloaded fCover in other date from "https://land.copernicus.vgt.vito.be/PDF/portal/Application.html#Home" then uploaded to your own GEE assets; this means you need do a minor mondifidation in this program to get your desired products;

so up to 2022-02-17, the daily, monthly, yearly CI products in 2019 are available for download;

After the corresponding data are already; all daily, monthly, yearly products can be downloaded from this code;

Notes: this code is designed to provide an interactive download tool; after you run this code in GEE, an UI page is appeared and you need type two dates (the start date and end date of products you want), then you can click to produce what products do you need and select to export a global or regional image to your Google derive;
Some instructions as following:
 1) please type date with a form likes "2020-01-01";
 2) please slow down you click speed in UI page because calculating CI is not a easy work;
 3) The global product will be divided to 9 single images to export because the same set in GEE, so do not be astonished when you see 9 pieces of Image in your google derive;
 4) All products include 2 bands (CI band and Quality band) and are named by its date, more information about products can see the reference in the end of this page;
 5) I give a name of exported folder ("CIFolder"), you can modify as you like;
The fast open link "https://code.earthengine.google.com/02b1ac3eb93bf94dda3adb266a1894a3"; The GEE app "https://lrvings.users.earthengine.app/view/civiewer" can be used to view products;

I strongly recommend you to cite the following references if you got help in your work form here; and please to share my work to your friends if they need;
[1] Wei, S. and H. Fang (2016). "Estimation of canopy clumping index from MISR and MODIS sensors using the normalized difference hotspot and darkspot (NDHD) method: The influence of BRDF models and solar zenith angle." Remote Sensing of Environment 187: 476-491.
[2] Wei, S., H. Fang, C. B. Schaaf, L. He and J. M. Chen (2019). "Global 500 m clumping index product derived from MODIS BRDF data (2001–2017)." Remote Sensing of Environment 232: 111296.
