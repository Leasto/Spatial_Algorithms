# GEO 877 - Spatial Algorithms 

## Project Overview

This project investigates the urban soundscape of Zurich using geotagged Flickr photographs and the methodology proposed by Aiello et al. (2016). Sound-related tags extracted from Flickr posts are classified into sound categories and spatially linked to street segments in order to identify dominant sound environments across the city.

The workflow consists of four main steps:

Filtering Flickr posts to the Zurich study area.
Classifying Flickr tags using a manually constructed sound taxonomy.
Segmenting the Zurich street network and creating buffer polygons around street segments.
Assigning Flickr sound tags to street segments using a point-in-polygon (ray casting) approach and identifying dominant sound categories.

## Data Sources
#### Flickr Data
Geotagged Flickr photographs from Switzerland
Original dataset filtered to a Zurich bounding box
Output: Flickr_ZURICH.csv
#### Street Network
Zurich street network stored as a shapefile
Coordinate reference system: EPSG:2056 (CH1903+ / LV95)

## Methodology
#### 1. Sound Taxonomy

A sound taxonomy was created based on the framework proposed by Aiello et al. (2016). Tags are grouped into five main sound categories:

- Transport
- Mechanical
- Human
- Music
- Nature
- Indoor
- 
Each category contains several subcategories and associated keywords.

#### 2. Sound Wheel

Flickr tags are matched against the sound taxonomy. The resulting tag frequencies are visualised using a sunburst chart (sound wheel) representing the hierarchical structure of sound categories.

#### 3. Street Segmentation

Street polylines are divided into segments with a maximum length of 1000 metres. This allows spatial sound information to be analysed at a finer resolution.

#### 4. Buffer Creation and Spatial Matching

A buffer polygon is generated around each street segment. Flickr points are assigned to street segments using a point-in-polygon test based on the ray casting algorithm.

#### 5. Dominant Sound Category

For every street segment, sound tags within the corresponding buffer are counted. The most frequent category is assigned as the dominant sound category for that segment.

## Software Requirements

Python packages used in this project:

pandas
numpy
matplotlib
plotly
geopandas

## Output

The project produces:

- A Flickr-derived sound wheel for Zurich
- Segmented street network data
- Buffered street segments
- A spatial sound map showing dominant sound categories across Zurich streets

## Reference

Aiello, L. M., Schifanella, R., Quercia, D., & Aletta, F. (2016). Chatty Maps: Constructing sound maps of urban areas from social media data. Royal Society Open Science, 3(3), 150690.

| | |
|---|---|
| **Authors:** | Muriel Geissmann, Julia Good & Lea Stoffl |
| **Course:** | GEO877 |
| **Institution:** | University of Zurich |
| **Semester:** | Spring Semester 2026 |


