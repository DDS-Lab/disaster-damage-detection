---
layout: page
title:  Methods and image processing
---
We considered several computer vision tasks to apply to our data, including classification, segmentation and object detection.  Classification would only allow us to identify whether a single object, for example, a damaged building was present in an image or not.  Segmentation would allow us to partition an image into multiple feature segments by pixels.  Since we were working with vector data, not raster data, this task would not be the most appropriate.  Segmentation has additionally been applied to flood detection in satellite imagery and has been used to extract bounding boxes around buildings, so we wanted to develop a model that would be complementary to these pre-existing tools.  We decided to apply object detection since it would allow for several object classes to be detected within each image without additional cropping.  Object detection would enable us to detect different objects that may be of interest to emergency managers, such as damaged buildings, damage debris, etc.  Within object detection many algorithms have been developed, however we mainly considered Faster R-CNN and Single Shot MultiBox Detector (SSD), since these methods were being applied to satellite imagery data during the xView detection challenge.  Using the SSD model that was pre-trained with 60 classes on DigitalGlobe satellite imagery at the xView challenge was most suitable for our timeline.  Once we had our models selected, we were ready to develop our pipeline.  The pipeline is fairly complex, but essentially we start with the raw data which we pass through a series of processes, such as image tiling, data processing, training data creation and model training and inference.

![Pipeline overview](Pipeline-processes2.png)

Details on the steps within each process are in the chart below.  For additional documentation and scripts, please visit our github repository [here](https://github.com/DDS-Lab/disaster-image-processing).

![Pipeline flow chart](Pipeline-large.png)


![Run alternatives](runalternatives.png)

