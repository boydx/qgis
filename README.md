# QGIS Short Course

Welcome to a workshop on QGIS. The intended audience 

## Overview

Within this short course you will:

* Gain a basic conceptual understanding of cartography, GIS, and mapping
* Gain familiarity with geographic data and information, and how it's encoded within computer files
* Download and install a free and open-source GIS application (QGIS)
* Create and query a spatial database
* Gain a basic familiarity with the QGIS interface
* Gain awareness of spatial reference and projection issues
* Practice opening a variety of geographic data with QGIS and viewing their attributes within QGIS
* Perform basic map styling
* Create and export a basic map as a static image file

## Short course audience and convention

This short course is geared towards working GIS professionals who have a general knowledge of ESRI ArcGIS. We will focus creating
 a production workflow that uses the unique features of QGIS not found in ArcGIS. This course is not solely intended to replace ESRI products, but rather compliment them. Since QGIS and associated tools are free and open source software (FOSS), it's a handy dimension to add to any GIS shop.
 
We use the following written conventions:

* Tools that you click will be bolded, e.g. **Project > New** to create a new QGIS project file. 
* Text that you’ll need to type will have quotes around it, such as, “My New Project” 
* Names of files and directories will be italicized, e.g., _datapage.zip_.
* Code that needs to be written and function parameters will be either ```inline``` or in a 

```SQL
/* Block of SQL code that needs to be entered in the DB Manager */

SELECT * FROM my_table
```
If the screenshots found in this document are too small to read, then __right+click__ the graphic and open in a new browser window.



## Data and project space

The following zip files contain spatial data that we'll use in this lesson.

* [Part 1: Making Lunch!](project_assets/module_part_01.zip), 11 MB
* [Part 2: Wildfire in Kentucky](project_assets/module_part_02.zip), 28 MB

Create a folder in the Z:/user/ directory called, *FirstNameGIS*, while substituting with your appropriate name. Please download and extract the data to this folder. Let's begin!



## About QGIS

![Accessing component information about QGIS](images/presentation/01_01.png)   
Figure: Accessing component information about QGIS.


![QGIS project is part of http://osgeo.org](images/presentation/02_01.png)   
Figure: QGIS project is part of [OSGeo](http://osgeo.org).

## Adding plugins and base maps

![User-contributed plugins are one of great assets of QGIS](images/presentation/03_01.png)   
Figure: User-contributed plugins are one of great assets of QGIS.

![OpenLayers plugin provides many raster base maps to help start a project](images/presentation/04_01.png)   
Figure: OpenLayers plugin provides many raster base maps to help start a project.

![Tile Server (XYZ) offers fast access to the growing world of raster base map tile sets.](images/presentation/05_01.png)   
Figure: Tile Server (XYZ) offers fast access to the growing world of raster base map tile sets.

![Web Mapping Services (WMS) is a traditional method of adding layers to a mapping project.o](images/presentation/06_01.png)   
Figure: Web Mapping Services (WMS) is a traditional method of adding layers to a mapping project.


![Layers in QGIS always have transparency options](images/presentation/07_01.png)   
Figure: Layers in QGIS always have transparency options.

### Spatial Bookmarks

![Use spatial bookmarks to set map canvas views.](images/presentation/08_01.png)   
Figure: Use spatial bookmarks to set map canvas views.

## Using OpenStreetMap data

![QuickOSM is one of the easiest ways to get OSM data in a mapping project](images/presentation/09_01.png)   
Figure: QuickOSM is one of the easiest ways to get OSM data in a mapping project.


![GeoJSON is the preferred format on Win and Mac OS and it __is__ editable.](images/presentation/10_01.png)   
Figure: GeoJSON is the preferred format on Win and Mac OS and it __is__ editable.


![Accessing the Style panel to change the appearance of features.](images/presentation/11_01.png)   
Figure: Accessing the Style panel to change the appearance of features.

### Measuring and interrogating OSM features

![Accessing Project Properties to control project.](images/presentation/12_01.png)   
Figure: Accessing Project Properties to control project.

![Change measurement units in the General tab.](images/presentation/13_01.png)   
Figure: Change measurement units in the General tab.

![Use the Identity tool to find attributes and measurements](images/presentation/14_01.png)   
Figure: Use the Identity tool to find attributes and measurements

![QuickOSM data adds actions to the Action Identify tool to find source information on OSM](images/presentation/15_01.png)   
Figure: QuickOSM data adds actions to the Action Identify tool to find source information on OSM.

### Rule-based symbology of OSM layers

![Add highway (travel) features to your project.](images/presentation/16_01.png)   
Figure: Add highway (travel) features to your project.

![Rule-based symbology uses SQL to select features.](images/presentation/17_01.png)   
Figure: Rule-based symbology uses SQL to select features.

![Symbol levels control what features draw first (on the bottom) and last (on the top).](images/presentation/18_01.png)   
Figure: Symbol levels control what features draw first (on the bottom) and last (on the top).


![ Label Panel adds dynamic labels for features.](images/presentation/19_01.png)   
Figure: Label Panel adds dynamic labels for features.

![Save and share complex layers styles with the QGIS .qml file.](images/presentation/20_01.png)   
Figure: Save and share complex layers styles with the QGIS .qml file.


![A simple travel map of campus.](images/presentation/21_01.jpg)   
Figure: A simple travel map of campus.

### Filtering OSM attributes

![Filter layers with SQL.](images/presentation/23_01.png)   
Figure: Filter layers with SQL.


![Easily use SVG artwork for point symbols.](images/presentation/24_01.png)   
Figure: Easily use SVG artwork for point symbols.

### Publish map in Print Composer

![Map layouts for export or print use the QGIS Print Composer, which can contain multiple layouts.](images/presentation/25_01.png)   
Figure: Map layouts for export or print use the QGIS Print Composer, which can contain multiple layouts.



![Automatically create georeferenced image on Export.](images/presentation/26_01.png)   
Figure: Automatically create georeferenced image on Export.


![Add the exported map into a QGIS Map Canvas.](images/presentation/27_01.png)   
Figure: Add the exported map into a QGIS Map Canvas.


![Measure the distance to the your preferred restaurant.](images/presentation/28_01.png)   
Figure: Measure the distance to the your preferred restaurant.


![Export the point layer as GeoJSON while controlling for CRS.](images/presentation/29_01.png)   
Figure: Export the point layer as GeoJSON while controlling for CRS.

## Geoprocessing with QGIS

![Feature blending modes can create visualizations of density.](images/presentation/02_02.png)   
Figure: Feature blending modes can create visualizations of density.


![Wildfire point locations](images/presentation/01_02.png)   
Figure: Wildfire point locations

```SQL
/* Analysis of wildfire point file */

-- Copy and paste into DB Manager

select 
	sum(fire_size) as total_fire_acres,
	fips_name
from 
	ky_wildfire
group by 
	fips_name 
order by 
	total_fire_acres;
```

### Using DB Manager and SpatiaLite to calculate rate of wildfire

![Create table in DB Manager menu with close attention to parameters.](images/presentation/03_02.png)   
Figure: Create table in DB Manager menu with close attention to parameters.

```SQL
/* Spatial join (aggregate) wildfire points by counties */

-- Copy and paste into DB Manager

insert into ky_wildfires_by_county 
	
	(
	name,
	population,
	cumulative_acres,
	geom 
	)

select
	ky_counties.name, 
	ky_counties.POP_ESTIMATE_2013, 
	sum(fire_size) as cumulative_acres,
	ky_counties.geom
from
	ky_counties, ky_wildfire
where
	st_intersects(ky_counties.geom,ky_wildfire.geom)
group by 
	ky_counties.name;
```
If you make a mistake with your query, just delete all attributes from the new table with the following statement:

```SQL
delete from ky_wildfires_by_county;
```
and rerun the corrected query.

![Map total acres by county (not normalized).](images/presentation/04_02.png)   
Figure: Map total acres by county (not normalized).

![Map total acres by county (not normalized).](images/presentation/05_02.png)   
Figure: Map total acres by county (not normalized).

![Map cumulative acres per person by county.](images/presentation/06_02.png)   
Figure: Map cumulative acres per person by county.


![Map cumulative acres per person by county.](images/presentation/07_02.png)   
Figure: Map cumulative acres per person by county.



![Map cumulative percentage burned by county.](images/presentation/08_02.png)   
Figure: Map cumulative percentage burned by county.

Use the following expression in the Style Panel to normalize by area: ```cumulative_acres/($area/43560)```.

![Map cumulative percentage burned by county.](images/presentation/09_02.png)   
Figure: Map cumulative percentage burned by county.

## Use QGIS Vector tools for analysis

![Save Shapefile to a new layer.](images/presentation/10_02.png)   
Figure: Save Shapefile to a new layer.


![Select attributes and CRS of new layer.](images/presentation/11_02.png)   
Figure: Select attributes and CRS of new layer.



![Select attributes and CRS of new layer.](images/presentation/12_02.png)   
Figure: Select attributes and CRS of new layer.

![Select attributes and CRS of new GeoJSON.](images/presentation/13_02.png)   
Figure: Join attributes by location does a Spatial Join 

![Pay close attention to tool parameters.](images/presentation/14_02.png)   
Figure: Pay close attention to tool parameters.

### Compare to intersect analysis in SpatiaLite

![Test for photo](images/presentation/15_02.png)   
Figure: Create new table in DB Manager

```SQL

/* Spatial join with point in polygon using SpatiaLite spatial index. PostGIS automatically uses the spatial index. */

-- Copy and paste into DB Manager

insert into ky_wildfires_by_blockgroup
	(
	name,
	area_acres,
	cumulative_fire_arces,
	population,
	geom 
	)

select
	ky_blockgroups.geoid10, 
	st_area(ky_blockgroups.geom)/43560,
	sum(fire_size) as cumulative_acres,
	ky_blockgroups.b01001e1, 
	ky_blockgroups.geom
from
	ky_blockgroups, ky_wildfire
where
	st_intersects(ky_blockgroups.geom,ky_wildfire.geom)
and

/* Use the spatial index query to limit our candidate points. */
    
    ky_wildfire.rowid 

    in (

        select rowid from SpatialIndex         
        where 
            f_table_name = 'ky_wildfire'
        and
            search_frame = ky_blockgroups.geom
        )
group by ky_blockgroups.geoid10;
```

![Normalize output layer by population.](images/presentation/16_02.png)   
Figure: Normalize output layer by population.


![Example of choropleth map.](images/presentation/19_02.png)   
Figure: Example of choropleth map.


![Publish the choropleth map in Print Composer](images/presentation/18_02.png)   
Figure: Publish the choropleth map in Print Composer.






## Course credits

![Test for photo](images/nmp.png)