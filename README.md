Locate
======

Resources for developers want to working with Landgate's Locate service (http://www.locate.wa.gov.au/)

MapId
======
The Locate mapId is 09372590152434720789-00913315481290556980

Layers
======
Contains the list of layers in Locate, along with their layerIds, layerKeys, 
links to their datasources, and additional metadata.
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
