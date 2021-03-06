
### Location coordinate encoding

To encode locations as coordinates, BrAPI follows the GeoJSON standard (RFC 7946). WGS84 is used as the geodetic datum spatial reference system and is the default used by most GPS tools. The BrAPI spec for GeoJSON only supports two of the possible geometries: Points and Polygons. 

A Point is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element, and is recorded in meters above the WGS84 reference ellipsoid. 

Point Example: [ -76.506042, 42.417373, 123 ]

A Polygon is an array of Linear Rings, with each Linear Ring defined as an array of Points. In this structure, a Polygon can include one or many geometric shapes which might be overlapping or separate. 

Polygon Example: [ [ [ -77.456654, 42.241133, 494 ], [ -75.414133, 41.508282, 571 ], [ -76.506042, 42.417373, 123 ], [ -77.456654, 42.241133, 346 ] ] ]

Note for Image Locations 

 + With most images, the Point geometry should be used, and it should indicate the longitude and latitude of the camera. 
 + For top down images (ie from drones, cranes, etc), the Point geometry may be used to indicate the longitude and latitude of the centroid of the image content, and the Polygon geometry may be used to indicate the border of the image content. 