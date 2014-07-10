GovHack-2014
============

Resources for developers at GovHack 2014 seeking to use Landgate's new SLIP system to access spatial information from the Western Australian Government.

The new SLIP platform is based on [Google Maps Engine](https://www.google.com/enterprise/mapsearth/products/mapsengine.html) and is currently in a pre-launch beta.


# What is SLIP?

Landgate is coordinating effort across the State Government to deliver a new Shared Location Information Platform (SLIP). This effort builds on the original SLIP, established in 2007, and is transforming the way SLIP is used through the Google Maps Engine (GME).

The delivery of the new SLIP began in 2013 with the launch of [locate.wa.gov.au](http://locate.wa.gov.au). This new service has made available to a whole new audience just some of the data shared by over 30 organisations through SLIP. Locate has been used over 2 million times since being launched last October, and has spurred the development of scores of new applications that leverage GME.

The journey continues through GovHack 2014, with a range of new service being shared with the developer community.


# What's available?

Rather a lot!

## Google Maps Engine - Development Environment

> To be written!


## Data

We're making three map services available for GovHack this year: Locate, our Resources Sector map service, and our Developer Sandbox service.

Use these links to preview the [Locate](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/mapview/?authuser=0) and [Resources](https://mapsengine.google.com/09372590152434720789-11493353092997567468-4/mapview/?authuser=0) services. To access the [Developer Sandbox](https://mapsengine.google.com/09372590152434720789-00440247219122458144-4/mapview/?authuser=0) contact Keith Moss ([Twitter](https://twitter.com/kevin_rudds_cat) or [Email](mailto:keith.moss@landgate.wa.gov.au)), Landgate's technical mentor.


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
* A subset of information from the 2011 Census
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

> To be written!

http://www.landgate.wa.gov.au/corporate.nsf/web/SLIP+Data+Dictionary


# How can I use SLIP in my project?

So you've seen the map viewers above, poked around, and found some data you want to use for your GovHack project. Great!

This section will serve as a *brief* overview and introduction to developing with the new SLIP platform. More detailed information, step-by-step guides, tutorials, code samples, and much more are available on our **[SLIP Developer Documentation](https://github.com/Landgate/slip-developer-documentation/wiki)** portal.


### layers.json
> To be written!

This JSON dump contains the list of layers in the map service, along with their layerIds, layerKeys, datasourceIds, URIs for their datasources, and some additional useful metadata.

```json
{
  layerId: /* A globally unique ID used to refer to this layer */
  layerKey: /* The layer key - For the GMaps JS Lib. Not unique. */
  name: /* The layer name */
  description: /* The layer description */
  bbox: /* An array of four numbers (west, south, east, north) which define
    the rectangular bounding box covered by the layer as latitude and longitude in decimal degrees */
  datasourceType: /* The type of layer - one of "table" or "image" */
  datasources: /* The path to the GME API resource of the more specific version of this asset.
    Used for querying features and only applies to datasourceType "image". */
}
```

For easier viewing of layers.json use the [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) Chrome extension or the free online [JSON Visualisation](http://chris.photobooks.com/json/default.htm) tool.

> **Coming Soon:** We're hard at work on a brand new search and discovery tool! We'll intergrate all of this information and more in a single easy to use web interface with handy tools for developers.


### Spatial? 0_o
If you're new to working with spatial data or mapping we highly recommend you spend some time reading these resources.

> [mapschool.io: a free introduction to geo](http://mapschool.io/)

> [GIS for Dummies (written by a dummy)](http://wiki.openstreetmap.org/wiki/GIS_for_Dummies_(written_by_a_dummy)

(it'll save you much head scratching and bafflement later on)

### A note on mapIds

> To be written!
>
> ***Locate's* mapId:** 09372590152434720789-00913315481290556980
>
> **Resources mapId:** 09372590152434720789-11493353092997567468


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

> To be written!
>
> **WMS:** Locate | Resources | Sandbox
>
> **WMTS:** Locate | Resource | Sandbox


#### Google Maps JavaScript API
The [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/tutorial) has connectors specifically [for Google Maps Engine](https://developers.google.com/maps/documentation/javascript/mapsenginelayers).

There are two means of connecting to Google Maps Engine:

1. Via the layerId (recommended - see ```layers.json```), or
2. By supplying a mapId and a layerKey.

> To be written!
> Locate:
>
> Resources:
>
> Sandbox:

> ***Locate's* mapID:** 09372590152434720789-00913315481290556980
>
> **Resources mapId:** 09372590152434720789-11493353092997567468

#### Desktop / Offline
For viewing and manipulating spatial data on the desktop you can't go past [QGIS](http://www.qgis.org/en/site/), the open source Geographic Information System.

> PostGIS

#### Other
For non-client facing calls you can either build the URLs  yourself; alternatively you can use existing libraries like [OWSLib (Python)](https://pypi.python.org/pypi/OWSLib) or [GeoTools (Java)](http://geotools.org/).

----

### I need to be able to retrieve and run queries against the raw data
If your focus is actually getting at the raw data itself, running queries against it, and analysing it then the [Google Maps Engine API](https://developers.google.com/maps-engine/) is your friend.

The GME API is a RESTful API that speaks and consumes JSON. Our [Getting Started](https://github.com/Landgate/slip-developer-documentation/wiki/Getting-Started) documentation and [GME API Tutorial](https://github.com/Landgate/slip-developer-documentation/wiki/Tutorial-%231%3A-The-GME-API-%26-WFS) have more information on working with the GME API. We've also got a few [code samples](https://github.com/Landgate/slip-code-samples) demonstrating more advanced uses of the GME API.

Accessing data via the Google Maps Engine API or WFS is at the datasource-level and requires a datasource assetId to be provided (see ```layers.json```).

> **GME API:** https://www.googleapis.com/mapsengine/v1/tables/{assetId}/features?version=published&key={your-api-key}

> **WFS:** https://clients6.google.com/mapsengine/wfs_experimental/wfs/{assetId}/?REQUEST=GetCapabilities&SERVICE=WFS2.0&assetVersion=published

#### Visualising GeoJSON
You can also map the GeoJSON data that the GME API returns. [OpenLayers](http://openlayers.org/dev/examples/?q=geojson) and [Leaflet](http://leafletjs.com/examples/geojson.html) support GeoJSON natively and GitHub itself [will render GeoJSON files](https://help.github.com/articles/mapping-geojson-files-on-github).

> *Note:* WFS access is available if needs be, but it's still an experimental service. See our [WFS page](https://github.com/Landgate/slip-developer-documentation/wiki/WFS) for more information.

#### Command-line
If command-line is more your thing there's work underway to support the GME API within the [GDAL](http://www.gdal.org/). See the [GMEDriver documentation](http://trac.osgeo.org/gdal/wiki/GMEDriver) for more information.

#### Error: *"This resource is too large to be accessed via this API call."*
If you receive this error message let us know and we can provide the details for an account with special access to larger data sources.


## Tools
### APIs
For playing with APIs we recommend use of the [Postman](http://www.getpostman.com/) HTTP Client. It makes exploring and testing APIs a breeze.

### Desktop Apps
If you need to manipulate, convert, and analyse spatial data [QGIS](http://www.qgis.org/en/site/) is the best open source Geographic Information System.

> PostGIS

### Make your own maps
If you have data you need to map you're spoilt for choice these days:

* [Google Maps Engine](http://mapsengine.google.com) (a free version of the same platform SLIP is built on (subject to [these limits](https://support.google.com/mapsengine/answer/3342103?hl=en)).
* [CartoDB](http://cartodb.com/)
* [TileMill](https://www.mapbox.com/tilemill/)
* [MangoMap](http://mangomap.com/)


# @TODO
* Some updates and tweaks from Unearthed feedback

* If I get time: A prettied up dump of the layers and data sources (inc. assetIds and endpoints) in the three services (since search isn’t public yet)
