Resources for developers want to work with Landgate's [*Locate*](http://www.locate.wa.gov.au) map service.

If you've stumbled upon this page without first reading out developer documentation please head [over there](https://github.com/Landgate/slip-developer-documentation/wiki) first for a lot of useful information about *Locate* and how to access SLIP Future.

## layers.json
Contains the list of layers in *Locate*, along with their layerIds, layerKeys, datasourceIds, URIs for their datasources, and some additional useful metadata.

```javascript
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

For easier viewing of layers.json try the [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) Chrome extension or the free online [JSON Visualisation](http://chris.photobooks.com/json/default.htm) tool.

> **Coming Soon:** Our brand new search and discovery tool! We'll intergrate all of this information and more in a single easy to use web interface.

## Accessing *Locate's* Data
How you access *Locate's* data depends on the API endpoints that you're using.

### The GME API & WFS
Accessing data via the Google Maps Engine API or WFS is at the datasource-level and requires a datasource assetId to be provided.

> **GME API:** https://www.googleapis.com/mapsengine/v1/tables/{assetId}/features?version=published&key={your-api-key}

> **WFS:** https://clients6.google.com/mapsengine/wfs_experimental/wfs/{assetId}/?REQUEST=GetCapabilities&SERVICE=WFS2.0&assetVersion=published

### Google Maps JavaScript API
The Google Maps JavaScript API has two ways of accessing data in Google Maps Engine:

1. Via the layerId (recommended), or
2. By supplying a mapId and a layerKey.

> ***Locate's* mapID:** 09372590152434720789-00913315481290556980


### WMS & WMTS
WMS and WMTS access to *Locate* only require the mapId.

> ***Locate's* mapID:** 09372590152434720789-00913315481290556980

**[WMS Capabilities](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/wms/?REQUEST=GetCapabilities&VERSION=1.3.0)** | **[WMTS Capabilities](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/wmts/?REQUEST=GetCapabilities&VERSION=1.0&SERVICE=WMTS)**
