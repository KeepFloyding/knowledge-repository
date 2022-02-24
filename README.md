# Knowledge Repository
A repository of papers and resources for research and knowledge consolidation.

* [Engineering](#engineering)
* [Physics Guided ML](#physics-guided-ml)
* [Data Set Generation](#data-set-generation)
* [Algorithms](#algorithms)
* [Transfer Learning in Process Industry](#transfer-learning-in-process-industry)

## Engineering

### Hydropower
For hydropower, there are 2 main modes of delivery: Dams and run of river. 

* [Mathematical Modeling of Hybrid Renewable Energy System: A Review on Small Hydro-Solar-Wind Power Generation](https://link.springer.com/content/pdf/10.1007%2Fs40684-014-0021-4.pdf)

Hybrid energy sources can be used to reduce the need for storage capacity and help mitigate intermittency.  Although an oversized hybrid system satisfies the load demand, it can be unnecessarily expensive. An undersized hybrid system is economical, but may not be able to meet the load demand. The optimal sizing of the renewable energy power system depends on the mathematical model of system components. Hybrid system has complex control system due to integration of two (or more) different power sources. The complexity of system increases with maximum power point tracking (MPPT) techniques employed in their subsystems. 

* [Modelling of a Hydro Power Station in an Island Operation](https://ep.liu.se/ecp/132/055/ecp17132483.pdf)

Representing a physical system of a hydropower plant by mathematical models can serve as a powerful tool for analysing and predicting the system performance during disturbances.  The main simulation scenarios of interest were: 20% load rejection, worst-case scenario of full shut-down and pressure rise in the pressure shaft due to the water hammer effect. Around 70% of Iceland’s electricity is produced from hydroelectric power and is the world’s largest electricity producer per capita. The load rejection simulation was constructed by a 20% sudden load rejection. This scenario is trying to imitate the incidence when there is a power shut-down, e.g.,, a shut-down of a large factory. The water hammer effect is particularly of interest for two reasons: There have been incidents where the pressure on the bottom of the pressure shaft raised above the pressure threshold of the pipe’s material, resulting in an outburst. Second reason is
the lack of surge tank in the power system. The objective of the surge tank is to absorb the pressure and therefore take care of the sudden pressure rise in the pressure shaft, like has been stated. I'm not sure what the conclusion is here.... 

![image](https://user-images.githubusercontent.com/29730122/155560068-d2fe0c0d-0042-4440-b0fc-2c1f2e2809ea.png)

The present paper intends to develop a correlation to determine the cost based on the influencing parameters such as power and head. An attempt has been made to develop the trend of the cost of electromechanical equipment with the increase in head of the hydropower plant.  Small hydro technology is extremely robust (systems can last for 50 years or more with little maintenance) and is also one of the most environmentally benign energy technologies available. 


* [Costing of a Small Hydropower Projects](http://www.ijetch.org/papers/357-P013.pdf)

The general formula for any hydro system’s power output is given by P=ηρgQh where, P is the mechanical power produced at the turbine shaft (Watts), h is the hydraulic efficiency of the turbine, ρ is the density of water (kg/m3), g is the acceleration due to gravity (m/s2), Q is the volume flow rate passing through the
turbine (m3/s), and h is the effective pressure head of water across the turbine (m). By using developed co-relation it has been found that the cost
of the electro-mechanical equipment decreases with increase in the head. This is because the size of the electro-mechanical equipment reduces with increase in the head. That is for high head small hydropower the cost of electro-mechanical equipment will be less as compared to the small head SHPs for the same capacity.

* [Machine Learning for Hydropower Scheduling: State of the Art and Future Research Directions](https://www.sciencedirect.com/science/article/pii/S1877050920320925) 

A review paper on how ML can be used for Hydropower applications. Normally the following techniques are used: Linear Regression, SVR, SVM, Clustering and ANN. The main goal is to do the following: Streamflow forecasting, hydropower consumption forecasting, reservoir inflow, hydropower generation projection, etc. 

Good paper, to be read more. 

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

* [Accelerated Bayesian inference-based history matching of petroleum reservoirs using polynomial chaos expansions](https://www.tandfonline.com/doi/full/10.1080/17415977.2021.1973455)

The traditional method employed in industry to perform history matching on reservoir simulations is based on manual selection of model parameters to match production history. Various methods to solve the inverse problems can be broadly classified into (i) deterministic methods and (ii) stochastic methods. A particular method can be classified as deterministic or stochastic depending upon the type of objective function of the inverse problem. To avoid the slow rate of convergence of the Genetic algorithms and the Evolutionary strategies, Bayesian inference (BI) based approaches have been developed in petroleum reservoir history matching. In BI, one starts with a prior distribution of model parameters, which is updated using the Bayes' rule, taking into account the production data, to get a posterior distribution of the model parameters. The most general method to implement BI is through the MCMC method, which is applicable to Gaussian and non-Gaussian prior distributions. However, due to the prohibitive computational cost of the MCMC method, computationally efficient approaches of performing Bayesian inference, such as the Ensemble Kalman Filter (ENKF), have been developed and such methods are based on various simplifying assumptions. The most commonly used methods to sample from the posterior distribution are the sequential Monte Carlo approach and the Markov Chain Monte Carlo (MCMC) method. The Bayesian inference along with MCMC is considered to be the standard method for history matching in reservoir modelling but it cannot be used directly for heavy reservoir simulation models due to the requirement of a large number of simulations which will be computationally expensive.

It seems that they use a meta-model for the reservoir simulations with something that is known as PCE (polynomial chaos expansion). This is to avoid the sampling of costly simulations. 

To read further...

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
