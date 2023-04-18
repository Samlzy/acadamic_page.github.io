---
layout: post
title: Multi-mode TEP Datasets
tags: dataset
math: true
date: 2022-4-17 00:00 +0800
---

*Multi-mode Tennessee Eastman Process Datasets*

## Description

The Tennessee Eastman Process (TEP) dataset is a widely used benchmark dataset in the field of chemical process control. It was originally created by the Tennessee Eastman Company as a simulated model of a chemical plant for the purpose of testing process control strategies. The dataset consists of measurements from 52 sensors and 23 control inputs, recorded over a period of 21 months, with a sampling interval of 5 minutes.

The TEP dataset is considered multi-mode, meaning that it contains multiple distinct operating modes or regimes. These modes correspond to different stages of the process, each with its own set of sensor readings and control inputs. The TEP dataset is widely used for developing and testing process control algorithms, as well as for benchmarking and comparing different methods. Its multi-mode nature makes it a challenging and realistic testbed for evaluating the robustness and adaptability of process control strategies.

We have made six modes of datasets in 72 hours, and there are 28 faults in every mode. All of them contain 12 variables of input, 41 variables of measurement and 28 variables of disturbance. The adjusted parameters are saved in *Mode1xInitial.mat* —*Mode6xInitial.mat*. The parameters of different modes are listed in Table I and Table II.

## Operation

User can adjust parameters to achieve different modes by themselves.

- Example (mode 2)

  1. Copy files  *Mode_1_Init.m, Mode1xInitial.mat and MultiLoop_mode1.mdl* and rename to *Mode_2_Init.m, Mode2xInitial.mat and MultiLoop_mode2.mdl*.
  2. Modify Mode1xInitial in 29 lines in *Mode_2_Init.m* to Mode2xInitial.
  3. Modify Mode_1_Init to Mode_2_Init by opening MultiLoop_mode2.mdl.
  4. Running *upda.m* and modify as follows:

     ```
     clear all;
     clc;
     load Mode2xInitial
     for i =1:35
         blockName = xInitial.signals(i).blockName;
         blockName(15) = '2';
         xInitial.signals(i).blockName = blockName;
     end
     save ('Mode2xInitial.mat','xInitial')
     ```

  5. Adjust the  parameters *MultiLoop_mode2.mdl* according to  Fig. 2 and Fig. 3. Note that the value of parameters adjusted each time should not be too large, otherwise the simulation will end quickly. And run the following code after each successful adjustment.

     ```
     xInitial = xFinal
     ```

  6. All parameters are adjusted to the final mode and run:

     ```
     save('Mode2xInitial.mat','xInitial')
     ```

For more details, please refer to the [*Github Repository*](https://github.com/liuzy0708/MultimodeTEP)
