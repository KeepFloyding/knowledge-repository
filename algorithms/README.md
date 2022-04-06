# Algorithms

## To be Read

* [Statistical Analysis of Simulation
Results](https://books-library.net/files/books-library.online-07071846Zc7R0.pdf)
* [Remove Initial Bias From Steady-State Stochastic
Simulation](https://fenix.tecnico.ulisboa.pt/downloadFile/844820067126245/dissertacao%20corrigida%20Laura%20Barroso%2073943.pdf)

## Anomaly Detection
* [Measurement of free surface deformation in PIV images](https://iopscience.iop.org/article/10.1088/0957-0233/16/10/012/meta)

A presentation of an anomaly detection algorithm that uses Studentized deleted residuals (from a polynomial regression curve) and the Bonferroni critical value to find outliers. Cool trick is presented that makes use of the projection matrix so as to avoid having to refit each data point. The method has been recreated and published [here](https://medium.com/cognite/studentized-residuals-for-time-series-anomaly-detection-b85862a2394c). More technical details about the method including derivations can be found [here](https://github.com/KeepFloyding/knowledge-repository/blob/main/algorithms/Studentized%20Residuals/docs/Derivations%20and%20General%20Info.pdf).


## Steady-State Detection
* [Online Steady-State Detection for Process Control Using Multiple Change-Point Models and Particle Filters](http://imse.utep.edu/mdasi/paper/paper4.pdf)

We proposed a robust online steady-state detection algorithm using multiple change-point model and particle filtering techniques. The goal of this method is to sequentially fit a piecewise linear model to a given time series. Particle filtering is well-proven to be able to estimate the parameters of a nonlinear system effectively. Commonly applied to object localization and tracking, the power of the particle filter comes in its ability to model parameter distributions that are non-Gaussian in nature. There are multiple different methods that have been used historically described as the offline and online methods. 

Offline methods include:
* Graphical methods such as visual inspection, CUSUM, exponentially weighted moving average and statistical process control method (SPC) models. 
* Heuristic rules such as MSER and MSER-5
* Statistical methods such as goodness-of-fit test and wavelet-based spectral method. 
* Initialization bias tests such as batch-means-based tests [9], students-tests and compound test method. 
* Hybrid methods which employ initialization bias tests in conjunction with graphical or heuristic approaches. Two methods of this type are the sequential method and the scale invariant truncation point method.

Online methods include:
* Slope detection method
* Performing a t-test on two recently computed means of two adjacent windows with pooled standard-deviation
* Monitoring the standard deviation of a moving window
* Performing an F-test on the ratio of variances of a moving window calculated using two different methods, the mean-squared-deviation and the mean of squared differences of successive data

These existing methods have certain limitations. One common disadvantage is that a data window has to be used. Too long a moving window may delay the detection while too short a moving window may increase the false detection rate. Another disadvantage is that the optimal detection parameters (i.e., window size, threshold) often depend on the characteristics of signals

Nice blog post about this can be found [here](https://medium.com/cognite/inso-insights-online-steady-state-detection-for-process-control-fae91567e560).
