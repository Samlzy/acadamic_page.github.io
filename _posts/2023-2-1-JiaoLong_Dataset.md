---
layout: post
title: JiaoLong DSMS Datasets
tags: dataset
math: true
date: 2023-2-1 00:00 +0800
---

*JiaoLong Deep-Sea Manned Submersible datasets (Life Support System)*

![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/jiaolong.png)
![GA](https://github.com/Samlzy/pics/raw/Samlzy-patch-1/Jiaolong_fig.jpeg)

## Description

The data used in this paper was collected and provided from the National Deep Sea Center in Qingdao, Shandong, China. The initial data is collected in the $$151^{st}$$ exploration task for the JiaoLong DSMS on March $$19^{th}$$, 2017.
The form of data is the multi-variate time series with around 11 features for about 3 hours. The sub-system of JiaoLong DSMS such as life support system is selected to analyze. Our purpose is to assess the safety level, such as safe level and unsafe level, for the tested data stream.

The seven variables of the life support system represent the real-time monitoring indicators, including oxygen ($$O_2$$) concentration in the cabin, carbon dioxide ($$CO_2$$) concentration in the cabin, cabin pressure (Pa), cabin humidity, and cabin temperature ($$^\circ$$C). In addition, backup 2 and backup 3 are also considered, representing the oxygen concentration of another set of oxygen sensors and the carbon dioxide concentration of another set of carbon dioxide sensors, respectively. Two settings of oxygen and carbon dioxide sensors are set up in the cabin as a backup to monitor the oxygen and carbon dioxide concentration at any time.  Hence, the monitoring data of backup 2 and backup 3 are the values of another set of oxygen and carbon dioxide sensors. Moreover, four settings of other external monitoring variables containing salinity, temperature, depth, and speed are selected. The monitoring data is sourced from the value of the conductivity temperature depth (CTD) sensor installed outside the JiaoLong DSMS, which monitors the real-time seawater salinity, temperature, depth, and the speed of ascending and descending.

During the experiment, the JiaoLong DSMS gradually descended from the shore to around 3000 meters. It is worth noting that the used labels are derived from the records of real voyage logs obtained in JiaoLong DSMS. The total number of samples is $$64138$$.

For more details, please refer to the [*Github Repository*](https://github.com/liuzy0708/JiaolongDSMS_datasets)
