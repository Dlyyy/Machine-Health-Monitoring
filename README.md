# Deep Learning and Its Applications to Machine Health Monitoring

This module contain the code used in our survey paper: [Deep Learning and Its Applications to Machine Health Monitoring](https://www.researchgate.net/publication/311839720_Deep_Learning_and_Its_Applications_to_Machine_Health_Monitoring_A_Survey). It has been accepted by [Mechanical Systems and Signal Processing](https://www.journals.elsevier.com/mechanical-systems-and-signal-processing). Pls find the newest version there. 

## Table of Contents

<!-- TOC START min:1 max:3 link:true update:true -->
- [Deep Learning and Its Applications to Machine Health Monitoring: A Survey](#DL-MHMS)
  - [Table of Contents](#table-of-contents)
  - [Data](#data)
  - [Code](#code)
    - [Feature Extraction](#feature-extraction)
    - [Deep Learning Models](#deep-learning-models)
    - [Machine Learning Models](#machine-learning-models)
    - [Main Test](#main-test)
<!-- TOC END -->



## Data
This folder contains two pickle files, which are extracted features and labels for tool wear sensing experiments. Each pickle file contain x_train, y_train, x_test, y_test. The task is defined as a regression problem.

- data_normal: each data sample is a vector. The features are extracted from the whole time sequences. 
- data_seq: each data sample is a tensor. The features are extracted from windows of the time time sequences. 

Especially, data_seq can be used by LSTM and CNN models. data_normal can be utilized by conventional ML models.
数据
此文件夹包含两个pickle文件，这些文件是工具磨损感应实验的提取特征和标签。 每个pickle文件包含x_train，y_train，x_test，y_test。 该任务被定义为回归问题。
data_normal：每个数据样本都是一个向量。 从整个时间序列中提取特征。
data_seq：每个数据样本都是张量。 从时间序列的窗口提取特征。
特别是，data_seq可以由LSTM和CNN模型使用。 data_normal可以由传统的ML模型使用。

## Code
This folder contains codes for feature extraction, traditional machine learning models, deep learning models and test modules. 

### Feature Extraction
RMS, VAR, MAX, Peak, Skew, Kurt, Wavelet, Spectral Kurt, Spectral Skewness, Spectral Powder features are extracted from the input time series. 

### Deep Learning Models
Based on Keras, autoencoder and its variants, implementations of DBN, LSTM, Bi-directional LSTM and CNN models are provided
基于Keras，autoencoder及其变体，提供DBN，LSTM，双向LSTM和CNN模型的实现

### Traditioanl Machine Learning Models
SVR with two kernels (linear and rbf), Random Forest and Neural Network are provided.

### Main Test
To replicate the results reported in paper (python 2.7)
```
pip install -r requirement 
python main_test.py
```
The results will be stored in output.log. In addition, a python notebook file is provided to parse the raw log file for mean and std accuracies computing. And due to randomness, we run all of these models five times. 
结果将存储在output.log中。 此外，还提供了一个python笔记本文件来解析原始日志文件的平均值和标准精度计算。 由于随机性，我们运行所有这些模型五次。

