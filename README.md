# Knowledge Repository
A repository of papers and resources for research and knowledge consolidation.

* [Engineering](https://github.com/KeepFloyding/knowledge-repository/tree/main/engineering/)
* [Physics Guided ML](#physics-guided-ml)
* [Data Set Generation](#data-set-generation)
* [Simulation Based Inference](#simulation-based-inference)
* [Algorithms](https://github.com/KeepFloyding/knowledge-repository/tree/main/algorithms/)
* [Transfer Learning in Process Industry](#transfer-learning-in-process-industry)

## To be read

* [Rejection of Outliers](https://www.stat.cmu.edu/technometrics/59-69/VOL-02-02/v0202123.pdf)

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

## Simulation Based Inference

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

* [Approximate Bayesian computation scheme for parameter inference and model selection in dynamical systems](https://www.researchgate.net/publication/23995500_Toni_T_Welch_D_Strelkowa_N_Ipsen_A_Stumpf_MPApproximate_Bayesian_computation_scheme_for_parameter_inference_and_model_selection_in_dynamical_systems_J_R_Soc_Interface_6_187-202) 

Approximate Bayesian computation (ABC) methods can be used to evaluate posterior distributions without having to calculate likelihoods. In this paper, we discuss and apply an ABC method based on sequential Monte Carlo (SMC) to estimate parameters of dynamical models. Traditional ABC methods (ABC rejection sampler) sample a parameter from the prior and use it to generate simulated data. If the agreement between simulated and experimental data is below a certain tolerance threshold, then that value for the parameter is rejected, otherwise it is used to update the posterior accordingly. The trouble with this method is that it can be expensive and slow to run if the prior distribution is a poor approximation to the true value. Thus there are alternative methods that are used such as MCMC (Markov Chain Monte Carlo) ABC models which have a proposal distribution for the parameters that can be used to alter the value of the parameter if there is a rejection. The authors in this paper propose an alternative which is known as ABC SMC (Sequential Monte Carlo) which is a little bit more complicated (it involves propogating the parameter through a series of intermediate distributions). They test their algorithm against several well known dynamical systems such as the Lotka-Volterra equations (deterministic and stochastic) and SIR (Susceptible, infectious and recovered) models.

* [Automatic Posterior Transformation for Likelihood-free Inference](https://arxiv.org/pdf/1905.07488.pdf)

ABC methods for SBI can suffer from the curse of dimensionality when a large number of summary statistics are used to compute the distance function. Posterior Estimation methods can surpass this by targeting the posterior directly. A recent approach is to learn the posterior from adaptively proposed simulations using neural network-based conditional density estimators. Classical approaches to such likelihood-free statistical inference (also known as Approximate Bayesian
Computation (ABC), do not scale to high-dimensional applications, and typically rely on ad-hoc choices to design summary statistics and distance functions. Posterior density estimation approaches directly target the posterior p(θ|x) by training a density-estimation neural network from (simulated) data x to θ. This approach does not require additional inference procedures, and thus naturally amortizes inference. In addition, it leverages the ability of neural networks to learn informative features from data.

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
