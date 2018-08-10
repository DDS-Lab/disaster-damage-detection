---
layout: page
title: Data collection
---
| Data Type| Source|Generation Method|Format|File Size Order|License|
| -------------- | ----------- | ------------ | ------------- |-------------- | ------------- |
| Imagery|[DigitalGlobe](https://www.digitalglobe.com/opendata/hurricane-harvey/post-event)| Satellite(RGB)|GeoTIFF|~3 TB|Creative Commons 4.0|
| Imagery|[NOAA](https://storms.ngs.noaa.gov/storms/harvey/index.html#7/28.400/-96.690)|Aerial(RGB)|GeoTIFF|~60 GB|[US Government Works](https://www.usa.gov/government-works)|
| Damage Annotations|[TOMNOD](https://www.digitalglobe.com/opendata/hurricane-harvey/vector-data)|Crowdsourced|Vector|~1 MB|Creative Commons 4.0|
| Damage Annotations|[FEMA](https://data.femadata.com/NationalDisasters/)|Assessed by FEMA|Vector|~20 MB|[US Government Works](https://www.usa.gov/government-works)|
| Building Footprints|[Oak Ridge National Lab](https://data.femadata.com/NationalDisasters/)|Proprietary Algorithm|Vector|~2 GB|[US Government Works](https://www.usa.gov/government-works)|
| Building Footprints|[Microsoft](https://github.com/Microsoft/Open-Maps/wiki/Microsoft-Building-Footprint-Release)| Proprietary Algorithm|Vector|~3 GB|Open Data Commons Open Database License|
|Parcel Data<sup>*</sup>|[Affected County Appraisal Districts](https://github.com/DDS-Lab/disaster-image-processing/blob/master/Parcel%20Data%20for%20Affected%20Counties%20-%20Sheet1.csv)|Assessed by Appraisers|Vector|~1 GB|Variable|

*Parcel data was collected by contacting each County Appraisal District Office

This project utilized [Digital Globe Data](https://www.digitalglobe.com/opendata/hurricane-harvey/post-event) which included Hurricane Harvey tif images and a geojson of volunteer crowdsourced damage annotations from TOMNOD, as well as aerial imagery from the National Oceanic and Atmospheric Administration (NOAA).

As our goal was to train a model to automatically detect damages in post-hurricane satellite imagery, we needed to gather all data required for our chosen machine learning algorithms: SSD and Faster R-CNN.  Since these required bounding boxes around the annotated damage points, we gathered parcel data and building footprints from the affected counties to create an additional layer from which the bounding boxes for the features (damaged and undamaged buildings) could be generated.  Find more details on the data collection process [here](https://github.com/DDS-Lab/disaster-image-processing/blob/master/data.md).

Now for a look a closer look at the imagery data:

![Satellite](Webp.net-gifmaker1.gif)

1. TOMNOD points (cyan) are downloaded from the Digital Globe website for the study area. Points represent locations of damaged buildings following Hurricane Harvey identified from satellite imagery from TOMNOD volunteers.

![png](https://github.com/DDS-Lab/disaster-damage-detection/blob/master/data1.png?raw=true)

2. The light green boxes represent 2048 X 2048-pixel chips of post-disaster satellite imagery coinciding with areas that were tagged by TOMNOD volunteers. We assume that the imagery contained in these bounds was reviewed by the TOMNOD volunteers to tag damaged buildings.

![png](https://github.com/DDS-Lab/disaster-damage-detection/blob/master/data3.png?raw=true)

3. Let's zoom in to inspect a cluster of annotated points in finer detail.

![png](https://github.com/DDS-Lab/disaster-damage-detection/blob/master/data4.png?raw=true)

4. Microsoft building footprints (purple) [hyperlink] are obtained for the study area. Because coverage of this dataset is not complete around our study area, we also use a building footprints dataset from FEMA (light blue) [hyperlink] where Microsoft building footprints are absent.

![png](https://github.com/DDS-Lab/disaster-damage-detection/blob/master/data6.png?raw=true)

5. Bounding boxes are instantiated as the minimum bounding rectangle (also known as the envelope) of the merged building footprint dataset.

![png](https://github.com/DDS-Lab/disaster-damage-detection/blob/master/data8.png?raw=true)

