---
layout: post
title: Concept Drift Datasets
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

- If you want to regenerate the dataset and import it directly, you can download *DataStreamGenerator.py* and put it under the file where your code is located, and then import the class.  
- Example:

```
from DataStreamGenerator import DataStreamGenerator

C = DataStreamGenerator(class_count=2, attribute_count=2, sample_count=100000, noise=True, redunce_variable=True)

X, Y = C.Nonlinear_Sudden_RollingTorus(plot=True, save=True)
``` 

- If you want to modify the source code, you can download it and do it in *DataStreamGenerator.py*.

For more details, please refer to the [*Github Repository*](https://github.com/THUFDD/THU-Concept-Drift-Datasets)
