# Khagrachhari-Flood-Inundation-Mapping-2026

# Sentinel-1 SAR-Based Flood Inundation Mapping of Khagrachhari — 2026 


Sentinel-1 SAR-based flood inundation detection and spatial analysis of Khagrachhari District, Bangladesh using Google Earth Engine and QGIS.
An end-to-end remote sensing and GIS workflow for mapping and analyzing flood inundation in Khagrachhari District, Bangladesh.



## Overview

This project presents an end-to-end workflow for detecting and analyzing flood inundation in Khagrachhari District, Bangladesh.

Sentinel-1 Synthetic Aperture Radar (SAR) imagery was processed in Google Earth Engine to generate a binary flood-inundation mask. The
resulting raster was then analyzed in QGIS for reprojection, clipping, area estimation, raster-to-vector conversion, and flood-patch analysis.

The project demonstrates the integration of cloud-based remote sensing processing with desktop GIS analysis to produce a reproducible flood mapping workflow.


## Study Area

The study focuses on Khagrachhari District in the Chattogram Division of Bangladesh.

The administrative boundary of Khagrachhari was used to define the analysis area and to constrain the flood-mapping results.
**Study area:** Khagrachhari District, Bangladesh

## Objectives

- Detect flood inundation using Sentinel-1 SAR imagery.
- Generate a binary flood-inundation mask.
- Estimate the detected flooded area.
- Reproject the flood raster to a projected coordinate reference system.
- Clip the raster to the study-area boundary.
- Convert the flood raster into vector polygons.
- Analyze the spatial distribution and size of detected flood patches.
- Produce a final cartographic flood map.

## Data Sources

### Sentinel-1 SAR

Sentinel-1 Synthetic Aperture Radar imagery was accessed through the Google Earth Engine data catalog and used for flood-inundation detection.

### Administrative Boundary

A Khagrachhari District administrative boundary dataset was used to define the study area and clip the flood-detection result.

> Third-party datasets and satellite imagery remain subject to their
> respective licenses and terms of use.

## Tools & Technologies

- **Google Earth Engine** — satellite-image processing and flood detection
- **JavaScript** — Google Earth Engine scripting
- **Sentinel-1 SAR** — flood detection data
- **QGIS** — raster and vector spatial analysis
- **GDAL** — raster processing
- **GeoTIFF** — raster data format
- **GeoPackage** — vector data format

## Workflow

The project follows the workflow below:

Sentinel-1 SAR imagery  
↓  
Image filtering and preprocessing  
↓  
Flood detection  
↓  
Binary flood mask generation  
↓  
GeoTIFF export  
↓  
Reprojection to UTM Zone 46N  
↓  
Clip by Khagrachhari boundary  
↓  
Flood-area calculation  
↓  
Raster-to-vector conversion  
↓  
Flood polygon selection  
↓  
Dissolve  
↓  
Multipart-to-singlepart conversion  
↓  
Flood-patch area calculation  
↓  
Spatial statistics  
↓  
Final cartographic visualization


## Results

The flood-detection raster contained two classes:

- `0` — non-flooded/background
- `1` — detected flooded area

The raster-based analysis produced the following results:

| Metric | Result |
|---|---:|
| Study area | 2,857.07 km² |
| Detected flooded area | 24.3894 km² |
| Flood pixels | 243,894 |
| Pixel size | 10 × 10 m |
| Detected flooded proportion | ~0.85% |



## Raster–Vector Consistency Check

The detected flood area was independently examined using both raster and vector representations.

| Method | Flooded Area |
|---|---:|
| Raster pixel calculation | 24.3894 km² |
| Polygon geometry calculation | 24.4016 km² |
| Difference | ~0.0122 km² |
| Relative difference | ~0.05% |

The small difference demonstrates close agreement between the raster
area calculation and the corresponding polygon geometry calculation.


## Flood-Patch Analysis

Following raster-to-vector conversion, the detected flood geometries
were dissolved and converted from multipart to singlepart geometries
for individual patch-level analysis.

The singlepart layer contains **18,339 features**.

A separate `patch_area_km2` field was calculated from the geometry using:


$area / 1000000




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


---

# 16. Limitations

The mapped inundation represents the output of the implemented Sentinel-1 SAR flood-detection workflow and should be interpreted as detected inundation rather than an independently validated flood inventory.

The analysis may be affected by factors such as radar backscatter variability, vegetation, terrain, permanent water bodies, image acquisition conditions, and the selected flood-detection parameters.

No independent ground-truth dataset is currently included in this repository.


## Future Improvements

Potential extensions of this project include:

- Independent validation using reference flood data.
- Comparison with optical imagery where cloud-free observations are available.
- Multi-date flood monitoring.
- Automated flood-area statistics.
- Flood severity classification.
- Integration of elevation and terrain variables.
- Development of a Google Earth Engine interactive dashboard.
- Integration of the results into a Bangladesh-wide environmental monitoring system.

## Reproducibility

The Google Earth Engine script and QGIS processing workflow are included in this repository to document the analysis.

The repository focuses on the processing workflow, derived results, and documentation rather than redistributing the original satellite imagery or third-party datasets.


## License

The original code and documentation in this repository are released under the MIT License.

Third-party datasets, satellite imagery, and other external resources remain subject to their respective licenses and terms of use.

## Author

**[Odri Chakma]**

GIS | Remote Sensing | GeoAI
Interested in geospatial data science, Earth observation, machine learning, and environmental monitoring.



```markdown



## Repository Structure

```text
Khagrachhari-Flood-Inundation-Mapping-2026/
│
├── README.md
├── LICENSE
│
├── gee/
│   └── khagrachhari_flood_mapping_2026.js
│
├── qgis/
│   └── workflow.md
│
├── maps/
│   └── Khagrachhari_Flood_Map_2026.png
│
├── results/
│   └── flood_statistics.csv
│
└── figures/
    └── workflow.png





