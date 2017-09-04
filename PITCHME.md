#HSLIDE
## Welcome!
### I'm Boyd, your instructor



#HSLIDE?image=images/outragegis.jpg
### I make maps for <a href="https://outragegis.com" target="_blank">trails</a>.

#HSLIDE?image=images/nmp.jpg
### Teach mapping at <a href="http://newmapsplus.uky.edu/" target="_blank">New Maps Plus</a>.

#HSLIDE?image=images/tbt.jpg
### Most recent map project using open source: <a href="http://boydx.github.io/tbt/" target="_blank">Town Branch Trail</a>.

#HSLIDE
## Raster analysis and tile set publishing
### with QGIS and GDAL utilities


#HSLIDE?image=https://www.outragegis.com/weather/goes16/current.jpg
### Do a lot of weather image processing: <a href="https://www.outragegis.com/weather/goes16/animation.gif" target="_blank">GOES-16 animation</a>.

#HSLIDE?image=images/intro/060.png
### Do scripting to process imagery: <a href="https://www.sheltoweetrace.com/hike/radar.html" target="_blank">radar overlay</a> and <a href="https://github.com/boydx/outrageGIS-weather-stations" target="_blank">source</a>.


#HSLIDE
## QGIS
### Free and open source software (FOSS)
Allows us to access many plugins that modify and analyze raster data <a href="http://download.qgis.org" target="_blank">download.qgis.org</a>.

#HSLIDE
## GDAL
### Geospatial Data Abstraction Library
A FOSS library that QGIS uses to process and transform raster data <a href="http://www.gdal.org/" target="_blank">http://www.gdal.org/</a>. It is available as standalone software accessed via command line.

#HSLIDE
## Get data
### Iroquois Park raster data
A 5-ft resolution DEM and 2-ft, 4-band 2016 NAIP data sets: <a href="https://github.com/boydx/qgis/project_assets/iroquois_park.zip" target="_blank">iroquois_park.zip</a>. 

#HSLIDE
## Get QGIS plugins
### Terrain Analysis & Qgis2threejs
and explore the Processing > Toolbox > GDAL/OGR


#HSLIDE
## Module 01
### Symbology
Explore and adjust raster contrast, rendering, and resampling settings.

* Load actual values
* Stretch to Min/Max to get show entire range with highest contrast
* Adjust saturation, brightness, etc.
* Select proper resampling technique; cubic vs. nearest neighbor.

#HSLIDE?image=images/intro/061.jpg


#HSLIDE
## Module 02
### 3D views
Qgis2threejs plugin can create an interactive environment to display and analyze DEM data.

#HSLIDE?image=images/intro/070.jpg



#HSLIDE
## Module 03
### Terrain Analysis
Create a hillshade raster with the Terrain analysis tool.

#HSLIDE?image=images/intro/080.jpg

#HSLIDE
## Module 04
### NDVI Analysis and canopy layer
Create a vegetation density index layer with the Raster Calculator tool using the equation:
```
 ( "IroquoisPark_NAIP_2016_2FT@4" - "IroquoisPark_NAIP_2016_2FT@1" )  /  ( "IroquoisPark_NAIP_2016_2FT@4" + "IroquoisPark_NAIP_2016_2FT@1")
 ```

#HSLIDE?image=images/intro/090.jpg

#HSLIDE
## Create canopy layer
### Add transparency and pseudo color
Adjust the transparency of the layer to omit estimated non-canopy pixels and make the remainder green.

#HSLIDE?image=images/intro/100.jpg

#HSLIDE
## Save canopy layer
### Render the NDVI layer 
Make the symbology permanent by rendering the layer during a right-click **Save As..**

#HSLIDE?image=images/intro/110.jpg

#HSLIDE
## Get data
### Load vector data from a file geodatabase
<a href="https://boydx.github.io/qgis/project_assets/data_in_file_geodatabase.zip" target="_blank">data_in_file_geodatabase.zip</a>

#HSLIDE
## Module 05
### Raster tile set creation
Use the gdal2tiles to create a slippy map layer

#HSLIDE?image=images/intro/120.jpg

#HSLIDE
## Module 06
###  OSGeo4W Shell
Make command line function using GDAL.

#HSLIDE?image=images/intro/125.jpg

#HSLIDE
## Data credits
### Kentucky from Above
### OpenStreetMap data: © OSM contributors





















