---
layout: post
title: Data -- Concept Drift Datasets
tags: dataset
math: true
date: 2022-4-17 00:00 +0800
---

*Simulted Concept Drift Datasets*

## Description

Concept drift describes unforeseeable changes in the underlying distribution of streaming data over time. Concept drift problem exists in many real-world situations, such as sensor drift and the change of operating mode. Detecting concept drift timely and accurately is of great significance for judging system state and providing decision suggestions. In order to better test and evaluate the performance of concept drift detection algorithm, we have made some datasets with known drift types and drift time points, hoping to help the development of concept drift detection.

## Usage

- If you want to use the datasets in the project, you can download them directly and import them using the pandas library.  
- Example:

```
import pandas as pd

data = pd.read_csv('xxxxxx/nonlinear_gradual_chocolaterotation_noise_and_redunce.csv')

data = data.values 

X = data[:, 0 : 5] 

Y = data[:, 5] 
``` 

- Or you can download *DatasetsInput.py*, and then import the class, as shown in *DatasetsInput_main.py*.(**Recommended**)
- Example:

```
from DatasetsInput import Datasets

Data = Datasets()

X, Y = Data.CNNS_Nonlinear_Gradual_ChocolateRotation()
``` 

- If you want to regenerate the dataset and import it directly, you can download *DataStreamGenerator.py* and put it under the file where your code is located, and then import the class.  
- Example:

```
from DataStreamGenerator import DataStreamGenerator

C = DataStreamGenerator(class_count=2, attribute_count=2, sample_count=100000, noise=True, redunce_variable=True)

X, Y = C.Nonlinear_Sudden_RollingTorus(plot=True, save=True)
``` 

- If you want to modify the source code, you can download it and do it in *DataStreamGenerator.py*.

## Dataset Introduction
We have made four categories of datasets, including *linear*, *rotating cake*, *rotating chocolate* and *rolling torus*. All of them contain four types of drifts: *Abrupt*, *Sudden*, *Gradual* and *Recurrent*. Users can choose whether to draw distribution of samples in real time, save pictures, and make sample change videos. Users can choose whether to add noise or redundant variables as well. See the picture below for a more detailed introduction. Note that the dataset name in the following figure is also the name of the intra class function.  

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/table1.png)

### Linear
In the dataset *Linear*, the decision boundary is a straight line. We simulate the change of the decision boundary through the rotation of the straight line. Users can freely select the rotation axis within the range of [-10, 10]×[-10, 10].

- Data distribution display:

* Gradual

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_linear_gradual_rotation_noise_and_redunce.gif)

* Sudden

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_linear_sudden_rotation_noise_and_redunce.gif)

* Recurrent 

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_linear_recurrent_rotation_noise_and_redunce.gif)

* Abrupt

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_linear_abrupt_noise_and_redunce.gif)


### CakeRotation
In the dataset *CakeRotation*, samples with odd angle area belong to one class, while samples with even angle area belong to another class. We simulate concept drift by rotating the disk, and the range of the angle area will change during the rotation. **If you need data sets of multiple categories, you can achieve it by using modulus instead of odd and even numbers on this basis[5].**
- Data distribution display:

* Gradual

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_gradual_cakerotation_noise_and_redunce.gif)

* Sudden

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_sudden_cakerotation_noise_and_redunce.gif)

* Recurrent 

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_recurrent_cakerotation_noise_and_redunce.gif)

* Abrupt

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_abrupt_cakerotation_noise_and_redunce.gif)


### ChocolateRotation
In the dataset *ChocolateRotation*, samples with odd *x+y* area belong to one class, while samples with even angle area belong to another class. We simulate concept drift by rotating the chocolate plate, and use the rotation matrix to calculate the coordinates of the samples in the new coordinate system and reclassify them. **If you need data sets of multiple categories, you can achieve it by using modulus instead of odd and even numbers on this basis.**
- Data distribution display:

* Gradual

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/nonlinear_gradual_chocolaterotation_noise_and_redunce.gif)

* Sudden

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_sudden_chocolaterotation_noise_and_redunce.gif)

* Recurrent 

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_recurrent_chocolaterotation_noise_and_redunce.gif)

* Abrupt

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_abrupt_chocolaterotation_noise_and_redunce.gif)


### RollingTorus
In the dataset *RollingTorus*, we set two torus of the same size close together, and the samples in different torus belong to different classes. We let the third torus roll over at a constant speed, and the samples overlapping the first two tori will become the opposite category. **If you need a dataset with unbalanced number of category samples, you can adjust the initial torus radius to achieve[6].**
- Data distribution display:

* Gradual

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_gradual_rollingtorus_noise_and_redunce.gif)

* Sudden

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_sudden_rollingtorus_noise_and_redunce.gif)

* Recurrent 

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_recurrent_rollingtorus_noise_and_redunce.gif)

* Abrupt

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/figure_nonlinear_abrupt_rollingtorus_noise_and_redunce.gif)


For more details, please refer to the [*Github Repository*](https://github.com/THUFDD/THU-Concept-Drift-Datasets)
