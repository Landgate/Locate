Resources for developers want to work with Landgate's [*Locate*](http://www.locate.wa.gov.au) map service.

This page is designed to be read alongside our [developer documentation for SLIP Future](https://github.com/Landgate/slip-developer-documentation/wiki).

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
What you need to access *Locate's* data depends on the API endpoints that you're using.

### The GME API & WFS
Accessing data via the Google Maps Engine API or WFS is at the datasource-level and requires a datasource assetId to be provided.

### Google Maps JavaScript API
The Google Maps JavaScript API has two ways of accessing data in Google Maps Engine:

1. Via the layer assetId (recommended), or
2. By supplying a map assetId and a layer key.

> ***Locate's* mapID:** 09372590152434720789-00913315481290556980


### WMS & WMTS
WMS and WMTS access to *Locate* only require the mapId.

> ***Locate's* mapID:** 09372590152434720789-00913315481290556980
