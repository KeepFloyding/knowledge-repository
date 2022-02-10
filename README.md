# Knowledge Repository
A repository of papers and resources for research and knowledge consolidation.


## General Info on Physics Guided ML

* [Review article on Physics-informed machine learning](https://www.nature.com/articles/s42254-021-00314-5.pdf).

To be read...

## Data Set Generation

* [Canonical Variate Dissimilarity Analysis for Process Incipient Fault Detection](https://ieeexplore.ieee.org/document/8304817)

Generation of a simplified CSTR model that creates a simulation based data set of normal operation and fault-induced anomalous operation. Model is subsequently used to test different multivariate statistical process monitoring methods. Model and paper results have been recreated here.

* [A pulp mill benchmark problem for control: problem description](https://www.sciencedirect.com/science/article/pii/S0959152403000118?via%3Dihub)

To be read...

* [A realistic and public dataset with rare undesirable real events in oil wells](https://www.sciencedirect.com/science/article/abs/pii/S0920410519306357?via%3Dihub)

This dataset contains several undesirable events related to subsea oil and gas production. It contains samples of real, simulated and sketched events from time series data that can be classified into 9 distinct categories (8 faulty and 1 normal). Additionally, the time series data within each event goes through 3 different phases and is correspondingly labeled as belonging to normal, transient or steady-state. 

* [Open Industrial Data: Inspiring Innovation & Fueling Collaboration in the Oil & Gas Ecosystem ](https://openindustrialdata.com/media/1065/open-industrial-data-cognite-akerbp.pdf)

Open Industrial Data is a data set that represents the first of four stages for compression of natural gas on the Valhall PH platform. The purpose of the gas train is to compress and treat the gas to meet the required export pressure and specification, with a total capacity of 4,06 MSm3/d (143 MMscf/d). The data set includes time series data, maintenance history, and Process & Instrumentation Diagrams (P&IDs) for Valhall’s first stage compressor and associated process equipment. This includes process equipment such as the suction cooler, suction scrubber, compressor and discharge coolers. 

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
