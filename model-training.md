---
layout: page
title: Model training
---
For more technical details on the steps involved in model training and inference, please visit our [github wiki](https://github.com/DDS-Lab/harvey_data_process/wiki).

For each training that we conducted, we were able to view the training loss and precision via the Tensorboard shown below:

![Tensorboard output](tensorboard-sat.png)

1. Satellite RGB Imagery from Digital Globe using Single Shot Detector (SSD)

![Damaged](damaged-sat.png)![Undamaged](undamaged-sat.png)

![groundtruth_test1](groundtruth_test1.png)

![groundtruth_test2](groundtruth_test2.png)

2. Aerial RGB Imagery from NOAA and FEMA

Red bounding boxes indicate damaged buildings and green bounding boxes indicate non-damaged buildings.

![NOAApredictions2class](noaapredictions.png)

![NOAApredictions2class2](noaapredictions2.png)

Green bounding boxes indicate non-damaged buildings and the other colored bounding boxes indicate damaged buildings of varying degrees.

![NOAA5class](NOAA5class.png)

![NOAA5class2](NOAA5class2.png)

