# Knowledge Repository
A repository of papers and resources for research and knowledge consolidation.

* [Physics Guided ML](#physics-guided-ml)
* [Data Set Generation](#data-set-generation)
* [Algorithms](#algorithms)
* [Transfer Learning in Process Industry](#transfer-learning-in-process-industry)


## Physics Guided ML

* [Review article on Physics-informed machine learning](https://www.nature.com/articles/s42254-021-00314-5.pdf).

To be read...

## Data Set Generation

* [Canonical Variate Dissimilarity Analysis for Process Incipient Fault Detection](https://ieeexplore.ieee.org/document/8304817)

Generation of a simplified CSTR (Continuous Stirred Tank Reactor) model that creates a simulation based data set of normal operation and fault-induced anomalous operation. Model is subsequently used to test different multivariate statistical process monitoring methods. Model and paper results have been recreated here.

* [A pulp mill benchmark problem for control: problem description](https://www.sciencedirect.com/science/article/pii/S0959152403000118?via%3Dihub)

To be read...

* [A realistic and public dataset with rare undesirable real events in oil wells](https://www.sciencedirect.com/science/article/abs/pii/S0920410519306357?via%3Dihub)

This dataset contains several undesirable events related to subsea oil and gas production. It contains samples of real, simulated and sketched events from time series data that can be classified into 9 distinct categories (8 faulty and 1 normal). Additionally, the time series data within each event goes through 3 different phases and is correspondingly labeled as belonging to normal, transient or steady-state. 

* [Open Industrial Data: Inspiring Innovation & Fueling Collaboration in the Oil & Gas Ecosystem ](https://openindustrialdata.com/media/1065/open-industrial-data-cognite-akerbp.pdf)

Open Industrial Data is a data set that represents the first of four stages for compression of natural gas on the Valhall PH platform. The purpose of the gas train is to compress and treat the gas to meet the required export pressure and specification, with a total capacity of 4,06 MSm3/d (143 MMscf/d). The data set includes time series data, maintenance history, and Process & Instrumentation Diagrams (P&IDs) for Valhall’s first stage compressor and associated process equipment. This includes process equipment such as the suction cooler, suction scrubber, compressor and discharge coolers.

## Simulation Based Inference (SBI)

* [The frontier of simulation-based inference](https://www.pnas.org/content/117/48/30055)

Simulators are poorly suited for statistical inference as the probability density (or likelihood) for a given observation is typically intractable. Such models are often referred to as implicit models and contrasted against prescribed models where the likelihood for an observation can be explicitly calculated. Two common traditional approaches rely on scientists to use their insight into the system to construct powerful summary statistics and then compare the observed data to the simulated data: probability density estimation and approximate Bayesian computation. New forces are causing there to be more development in this field:
* Idea of active learning is catching on; i.e. incrementally guiding a simulator with Bayesian inference.
* Also cross-pollination between simulators, machine learning and probablity modelling. 

* [Benchmarking Simulation-Based Inference](https://arxiv.org/pdf/2101.04653.pdf)

Paper provide a benchmark with inference tasks and suitable performance metrics. The goal of simulation-based inference (SBI), also known as ‘likelihood-free inference’, is to perform Bayesian inference without requiring numerical evaluation of the likelihood function. Difficult to compare between different approaches becauses tudies use different tasks and metrics for comparison. They conclude that the choice of performance metric is critical, the performance of
the algorithms on some tasks leaves substantial room for improvement, sequential estimation generally improves sample efficiency. An important difference between algorithms is how new simulations are acquired: Sequential algorithms adaptively choose informative simulations to increase sample efficiency. Algorithms are:

* REJ-ABC and SMC-ABC (Monte Carlo ABC) -> Monte Carlo Rejection Sampling
* NLE and SNLE (Likelihood Estimation -> learn an approximation to the intractable likelihood
* NPE and SNPE (Posterior Estimation) -> instead of approximating the likelihood, approaches target the posterior directly
* NRE and SNRE (Ratio Estimation)  -> use classifiers to approximate density ratios

The ‘gold standard’ would be to quantify the similarity between the true posterior and the inferred one with a suitable divergence measure on probability distributions.


## Algorithms

* [Measurement of free surface deformation in PIV images](https://iopscience.iop.org/article/10.1088/0957-0233/16/10/012/meta)

A presentation of an anomaly detection algorithm that uses Studentized deleted residuals (from a polynomial regression curve) and the Bonferroni critical value to find outliers. Cool trick is presented that makes use of the projection matrix so as to avoid having to refit each data point. Algorithm is recreated on a test data set under algorithms/t-res-anomaly-detector.ipynb. 

## Transfer Learning in Process Industry

* [Transfer learning for process fault diagnosis: Knowledge transfer from simulation to physical processes, Li et al. 2020](https://www.sciencedirect.com/science/article/pii/S0098135420301915)
 
 Using simulated data to train deep neural networks (convolutional neural network) and overcoming model-process mismatch with transfer learning (advanced domain adaptation technique). Application to 2 different use-cases continuously stirred tank reactor and the pulp mill plant benchmark problem. This is more for for Fault Detection and Diagnosis (FDD)
 
 * [Soft Sensor Transferability: A Survey, Curreri et al. 2021](https://www.mdpi.com/2076-3417/11/16/7710/pdf)

A review of how transfer learning techniques are applied to accomodate challenges in soft sensor (otherwise known as virtual sensor) design and provides a holistic overview of different transfer learning techniques. The existing literature demonstrates that TL can significantly enhance the
SS performance, designing SSs that can both face cross-phase and cross-entity scenarios.

* [Unsupervised Anomaly Detection on Streaming Data in the Petroleum Industry Using Deep Neural Networks, Reiten and Kleiven 2019](https://ntnuopen.ntnu.no/ntnu-xmlui/bitstream/handle/11250/2639893/no.ntnu:inspera:2525188.pdf?sequence=1)

Master's thesis from NTNU on using Open Industrial Data to build a data driven model that aims to do a one step ahead prediction of key compressor outlet variables (discharge pressure, temperature and flow rate). 6 inputs are chosen for this which are compressor suction temperature, pressure in scrubber, pressure drop between separator and compressor suction, anti-surge valve, suction cooler outlet temperature and power supplied to compressor. Mutiple models are tested such as LSTM, GRU, MLP and an ensemble LSTM/MLP with the latter showing the best performance in minimising MAE. The temporal granularity that is used is 1 minute. 

* [Development of Robust and Physically Interpretable Soft Sensor for Industrial Distillation Column Using Transfer Learning with Small Datasets, Hsiao et al 2021](https://pdfs.semanticscholar.org/4888/d2e01373ad959fbf95b293dc016c1d4e5ff8.pdf)

Methodology for combining first-principle simulations and transfer learning to avoid overfitting deep learning models on limited plant data.  This was applied to an industrial C4 separation column operating at a refining unit as an example to illustrate the effectiveness of this approach. Transfer learning was achieved by fine-tuning the parameters (weights and bias) of the networks (fine-tuning deep layers while freezing shallow ones) with the limited available plant data. Results showed that fine-tuned networks could obtain better accuracy and improved interpretability compared to a simple feedforward network with or without regularization.
