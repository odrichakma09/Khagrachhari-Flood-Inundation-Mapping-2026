

## QGIS Processing

The exported flood raster was processed in QGIS through the following
steps:

- Reprojection from EPSG:4326 to EPSG:32646
- Clipping by the Khagrachhari administrative boundary
- Raster statistics and flooded-area calculation
- Raster-to-vector conversion
- Selection of flood class (`DN = 1`)
- Dissolution of flood geometries
- Multipart-to-singlepart conversion
- Patch-area calculation
- Statistical analysis
- Cartographic map preparation
