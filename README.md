GovHack 2014
============

> After our documentation for GovHack 2015? Head on over to https://github.com/Landgate/GovHack-2015 :)

Hi there,

Herein you shall find a collection of resources to help you use Landgate's new SLIP system in your GovHack 2014 project. Our new SLIP platform is based on [Google Maps Engine](https://www.google.com/enterprise/mapsearth/products/mapsengine.html) and is currently in a pre-launch beta.


# What is SLIP?

Landgate is coordinating effort across the State Government to deliver a new Shared Location Information Platform (SLIP). This effort builds on the original SLIP, established in 2007, and is transforming the way SLIP is used through Google Maps Engine (GME).

The delivery of the new SLIP began in 2013 with the launch of [locate.wa.gov.au](http://locate.wa.gov.au). This new service has made available to a whole new audience just some of the data shared by over 30 organisations through SLIP. Locate has been used over 2 million times since being launched last October, and has spurred the development of scores of new applications that leverage GME.

The journey continues through GovHack 2014, with a range of new service being shared with the developer community.


# What's available?

## Google Maps Engine

We're happy to be making the development version of our [Google Maps Engine](https://www.google.com/enterprise/mapsearth/products/mapsengine.html) environment available to participants in GovHack. GME allows you to utilise the technology that went into Google Maps to create your own maps and geospatial applications, as well as load and rendering your own spatial data sets; all on Google’s world-class infrastructure.

If you're interested in using GME please contact [Keith Moss](https://twitter.com/kevin_rudds_cat), Landgate's technical mentor.


## Data

We're making three map services available for GovHack this year: Locate, our Resources Sector map service, and our Developer Sandbox service.

Use these links to preview, and perform basic queries, on the [Locate](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/mapview/?authuser=0) and [Resources](https://mapsengine.google.com/09372590152434720789-11493353092997567468-4/mapview/?authuser=0) services. To access the [Developer Sandbox](https://mapsengine.google.com/09372590152434720789-00440247219122458144-4/mapview/?authuser=0) contact [Keith Moss](https://twitter.com/kevin_rudds_cat), Landgate's technical mentor.


### Locate
[Locate](http://locate.wa.gov.au) was the first public map service launched on our new SLIP platform. It contains a wealth of data from over 30 organisations across the Western Australia Government, including:

* Property boundaries and sales records
* A high resolution aerial photo mosaic of Western Australia
* A collection of historical aerial photos dating back to 1948, and historic maps back to 1838
* Government boundary information, including:
  * State Electorates
  * Local Government Boundaries (current and proposed)
  * Suburbs
  * Aboriginal & Torres Strait Islands Boundaries (national dataset)
* The locations of schools, universities, hospitals, and emergency services
* Transport infrastructure, including:
  * Bus stops and routes
  * Train stations
  * Roads and rail lines
* Mining tenements and minerals deposits
* A cut of information from the 2011 Census
* Information on the sewer system, water pipes, and water meters.


### Resources Service
Our Resources Sector map service is the first of six public map themed map services we are rolling out over the remainder of this year. It includes a range of data sets focused on the resources and mining sector, including:

* Environmental data, including:
  * Regionally Significant Natural Areas (Swan Bioplan)
  * Supporting Information for Environmental Referral (EPA)
* Mining and resources data, includling:
  * Mineral drillholes and geothermal releases and titles
  * Mines and mineral deposits, mining tenements
  * Petroleum title, wells, applications, pipelines, and releases
* Native Title determinations and Indigenous Land Use Agreements
* Aboriginal communities and heritage places
* Geological and Geophysical data, including:
  * The regolith and bedrock geology of Western Australia
  * The geological map of Western Australia
  * Mineral field boundaries
  * Groundwater salinity across Western Australia
  * Acid sulfate soil risk maps
* Utilities data, including high voltage distribution and transmission lines


### Developer Sandbox

Our [SLIP Academy](https://groups.google.com/forum/#!forum/slip-academy) Developer Sandbox Service is a private service setup to allow developers to experiment with a geographically clipped range of data sets, including data usually reserved for subscribers SLIP. Data are clipped to cover the new suburbs around Clarkson, within an area stretching from Tamala Park in the south to Eglinton in the north.

* Aerial photography from 1956 - 2013.
* Infrastructure, including:
  * Bus stops and routes
  * Roads
  * Sewer pipes and access chambers
  * Water pipes and meters
* 2011 Census - Selected Medians and Averages (SA1) B02
* Administrative boundaries, including suburb and LGAs
* Geodetic horizontal control points

Subscription data available includes:

* Tenure data (property ownership information with names scrubbed)
* Cadastre, including: property polygon and address, boundary lines, and reserves
* Building footprints
* R-Codes
* Points of Interest


# I don't understand the data!

If you're having trouble understanding any of our data check out our [data dictionaries](http://www.landgate.wa.gov.au/corporate.nsf/web/SLIP+Data+Dictionary) resource for in-depth descriptions of our core datasets. If you require any further assistance, or can't find the data dictionary please contact Keith Moss, our technical mentor.


# How can I use SLIP in my project?

So you've seen the map viewers already, poked around, and found some data you want to use for your GovHack project. Great!

This section will serve as a *brief* overview and introduction to developing with the new SLIP platform. More detailed information, step-by-step guides, tutorials, code samples, and much more are available on our **[SLIP Developer Documentation](https://github.com/Landgate/slip-developer-documentation/wiki)** portal.


### A brief word on mapIds, layerIds, and datasourceIds

Throughout this documentation we'll refer variously to mapIds, layerIds, and datasourceIds. Don't worry, they're just unique identifiers for assets in SLIP.

Our mapIds are:

> **Locate:** 09372590152434720789-00913315481290556980
>
> **Resources:** 09372590152434720789-11493353092997567468
>
> **Sandbox:** 09372590152434720789-00440247219122458144

For layerIds and datasourceIds check out our ```layers.json``` dumps for:

> **[Locate](https://github.com/Landgate/Locate), [Resources](https://github.com/Landgate/Unearthed), or [Sandbox](https://github.com/Landgate/Sandbox)**

(For easier viewing of ```layers.json``` use the [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) Chrome extension, or the free online [JSON Visualisation](http://chris.photobooks.com/json/default.htm) tool)

> **Coming Soon:** We're hard at work on a brand new search and discovery tool! We'll intergrate all of this information and more in a single easy to use web interface with handy tools and links for developers.


### Spatial? 0_o
If you're new to working with spatial data or mapping we highly recommend you spend some time reading these resources.

> [mapschool.io: a free introduction to geo](http://mapschool.io/)

> [GIS for Dummies (written by a dummy)](http://wiki.openstreetmap.org/wiki/GIS_for_Dummies_(written_by_a_dummy)

(Trust us - it'll save you much head scratching and bafflement later on)


### I just need to be able to see something on a map
If you just need to be able to generate a visual representation of the data (e.g. display it on a map, generate once-off images) you have three APIs available:

* WMS: A RESTful API (Web Mapping Service)
  > A WMS returns JPEG/PNG images for one or more layers in a map service; as well as supporting querying the data ("tell me about the features at a point").
* WMTS: A RESTful API (Web Map Tiling Service)
  > A WMTS returns 256x256 JPEG/PNG images for a singe layer in a map service; it  also supports querying the data.
* Google Maps JavaScript API
  > The Google Maps JavaScript API implements its own version of a WMS-like interface via [MapsEngineLayer](https://developers.google.com/maps/documentation/javascript/mapsenginelayers). It also supports client-side rendering and styling of data via [DynamicMapsEngineLayer](https://developers.google.com/maps/documentation/javascript/mapsenginelayers#dynamicmapsenginelayer_events).

To consume any of these APIs you'll want a client library to do the heavy lifting for you. Fortunately you're spoilt for choice!

#### WMS & WMTS
[OpenLayers 2](http://openlayers.org/), [OpenLayers 3](http://ol3js.org/), [Leaflet](http://leafletjs.com/), amd [MapBox JS](https://www.mapbox.com/mapbox.js) can all be used to easily consume WMS and WMTS services.


> **WMS:** [Locate](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/wms/?REQUEST=GetCapabilities) | [Resources](https://mapsengine.google.com/09372590152434720789-11493353092997567468-4/wms/?REQUEST=GetCapabilities) | [Sandbox](https://mapsengine.google.com/09372590152434720789-00440247219122458144-4/wms/?REQUEST=GetCapabilities)
>
> **WMTS:** [Locate](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/wmts/?REQUEST=GetCapabilities) | [Resources](https://mapsengine.google.com/09372590152434720789-11493353092997567468-4/wmts/?REQUEST=GetCapabilities) | [Sandbox](https://mapsengine.google.com/09372590152434720789-00440247219122458144-4/wmts/?REQUEST=GetCapabilities)]

> **Note:** When referring to layers in WMS and WMTS remember to prepend ```-4``` to the layerId.


#### Google Maps JavaScript API
The [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/tutorial) has connectors specifically [for Google Maps Engine](https://developers.google.com/maps/documentation/javascript/mapsenginelayers).

There are two means of connecting to Google Maps Engine:

1. Via the layerId (recommended - see ```layers.json```), or
2. By supplying a mapId and a layerKey.


----


### I need to be able to retrieve and run queries against the raw data

If your focus is actually getting at the raw data itself, running queries against it, and analysing it then the [Google Maps Engine API](https://developers.google.com/maps-engine/) is your friend.

The GME API is a RESTful API that speaks and consumes JSON. Our [Getting Started](https://github.com/Landgate/slip-developer-documentation/wiki/Getting-Started) documentation and [GME API Tutorial](https://github.com/Landgate/slip-developer-documentation/wiki/Tutorial-%231%3A-The-GME-API-%26-WFS) have more information on working with the GME API. We've also got a few [code samples](https://github.com/Landgate/slip-code-samples) demonstrating more advanced uses of the GME API.

Accessing data via the Google Maps Engine API is at the datasource level and requires a datasourceId to be provided (see ```layers.json``` above).


#### Visualising GeoJSON
You can also map the GeoJSON data that the GME API returns. [OpenLayers](http://openlayers.org/dev/examples/?q=geojson) and [Leaflet](http://leafletjs.com/examples/geojson.html) support GeoJSON natively and GitHub itself [will render GeoJSON files](https://help.github.com/articles/mapping-geojson-files-on-github).


#### Command line
If command-line is more your thing there's work underway to support the GME API within the [GDAL](http://www.gdal.org/). See the [GMEDriver documentation](http://trac.osgeo.org/gdal/wiki/GMEDriver) for more information.

#### Error: *"This resource is too large to be accessed via this API call."*
If you receive this error message, let us know, and we can provide the details for an account with special access to larger data sources.


## Tools for working with spatial data
### APIs
For playing with any of our APIs we recommend use of the [Postman](http://www.getpostman.com/) HTTP Client. It makes exploring and testing APIs a breeze.


#### Offline Processing & Desktop Software
For spatial databases consider nothing but the best: the [PostGIS](http://postgis.net/) extension to PostGreSQL. If there's a spatial query or manipulation you need to do then PostGIS has it; and a hundred other functions besides.

For viewing and manipulating spatial data on the desktop you can't go past [QGIS](http://www.qgis.org/en/site/), the open source Geographic Information System.

For command line tools check out [GDAL](http://www.gdal.org/) (Geospatial Data Abstraction Library), which has readers and writers for over 50 types of spatial data. GDAL bindings also exist in Python, .NET, et cetera.


#### Code Libraries
For non-client facing calls you can either build the URLs  yourself; alternatively you can use existing libraries like [OWSLib (Python)](https://pypi.python.org/pypi/OWSLib) or [GeoTools (Java)](http://geotools.org/).

### Make your own maps
If you have data you want to load into a system to render and map you're spoilt for choice these days:

* [Google Maps Engine](http://mapsengine.google.com) (as noted earlier - our development environment is available).
* [CartoDB](http://cartodb.com/)
* [TileMill](https://www.mapbox.com/tilemill/)
* [MangoMap](http://mangomap.com/)
