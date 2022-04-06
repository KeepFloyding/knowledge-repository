

# Oil and Gas

## Virtual Flow Meters

* [First Principles and Machine Learning Virtual Flow Metering: A Literature Review](https://www.sciencedirect.com/science/article/pii/S0920410519309088)

At the early stage of the industry, the main method to estimate well flowrates was well testing. Here, a well stream is directed into a test separator where it is split into oil, gas and water. These flow streams are then measured by single-phase meters at the separator outlet. Over the last 25 years, physical multiphase flow meters (MPFMs) have been developed as an alternative solution to well testing to measure well multiphase flowrates and were first commercialized in the early 1990s. These meters are usually installed at the wellhead, so that the multiphase flowrates from a particular well can be tracked in real-time. The idea behind VFM is to collect available field data and use it in a numerical model to estimate flowrates. The sensor data typically used includes Bottomhole pressure and temperature, choke opening, wellhead pressure and temperaure and flowline pressure and temperature. 

At the same time, VFM systems have capabilities to estimate the flowrates in real time and reflect changes of flow conditions accordingly. This is a clear advantage compared to the well testing approach which assumes constant well flowrates between the tests. Based on modeling paradigms, two main Virtual Flow Metering approaches can be distinguished: first-principles and data-driven VFMs (I would argue that there is also a third one called Hybrid which aims to use a combinatio of the 2 approaches).  If the model is well trained and the exposed conditions are within the range used for the training, the data-driven model can perform fast and accurate real-time metering. In this approach, deep domain knowledge of production engineering is not as important as in the first principles models and the model can be constructed at a lower cost.

While it is possible to formulate the VFM optimization problem in a dynamic way, in the available literature on the first principles VFM does not consider this approach. The main reason for this may be the fact that dynamic optimization for first principles VFM systems is computationally very expensive.Apart from dynamic optimization, state estimation techniques such as Kalman filter approaches can be used in order to create a dynamic VFM. This approach has been covered in the research as we will show in the future sections, however, it is not implemented in the commercial software yet.

First principles model overview:
![image](https://user-images.githubusercontent.com/29730122/160296107-0405af55-904c-45bd-8433-806a3392f837.png)

State-of-the-art VFM systems support both compositional and BOM approaches for PVT modeling. The current trend in the first principles VFM is to use the compositional approach. When the fluid models are tuned to the specific fluid properties, the PVT tables for the expected range of pressure and temperature conditions is generated and uploaded into a VFM system. Using these data, the system can interpolate the computed properties (e.g. phase density and viscosity) to local pressure and temperature (e.g. at the wellhead) based on the specified table values. 

The Production System Model can be composed of many different parts, namely Reservoir Inflow Model, Thermal Hydraulic Model and Choke Model. 

### Reservoir Inflow Model

The reservoir inflow model is usually represented by an Inflow Performance Relationship (IPR) model which defines the well production rate as a function of pressure difference at reservoir and bottomhole conditions. The data for IPR curves are collected during multi-rate well testing. There are different models in use such as Linear, Backpressure, Undersaturated, Vogel, IPR table and Forcheimer. As an illustration, a linear model is defined as 

![image](https://user-images.githubusercontent.com/29730122/160296510-bb80fed3-a9a7-44d4-914d-fc47bb0a9f8d.png)

As we can see, the IPR models have variety of forms depending on the well production conditions. In VFM, IPR models can be used in different purposes. First, it can be used as a separate model to estimate the production potential of a well. Secondly, the IPR models can be used in a combination with the thermal-hydraulic and choke models as a boundary condition of the system representing reservoir inflow to the well. 

### Thermal Hydraulic Model

The first attempt to model the multiphase flow was made by Lockhart and Martinelli (1949). At that time, the approach for multiphase flow modeling was based on empirical correlations obtained from experiments and available field data. With time, a more fundamental modeling approach replaced pure empirical models by including the physics behind the multiphase flow phenomena.  Based on the literature, the following types of thermal-hydraulic multiphase models are currently implemented in the first principles VFM products: two-fluid model, drift-flux model and steady-state mechanistic model. 

In the two-fluid model (often referred as the multi-fluid model), the conservation equations are written for each phase which can be continuous or dispersed. In a simplified manner, the general form of mass, momentum and energy equations respectively. In the drift-flux model, the momentum and energy equations are written for the mixture while the mass conservation equations can be written for each phase. The drift-flux model requires a slip relation in order to take the difference between the phase velocities into account. The most famous and commonly used form is developed by Zuber and Findlay (1965). The drift-flux model requires a slip relation in order to take the difference between the phase velocities into account. The most famous and commonly used form is developed by Zuber and Findlay (1965). 

 van der Geest et al. (2000) formulated the momentum equation in a very generic way as the following:
 ![image](https://user-images.githubusercontent.com/29730122/161018751-235107de-741a-4b25-b744-88707b5eff1d.png)

### Choke Model

In addition to this, because the pressure drop over the choke depends on the flowrate, the choke valve can be used to estimate the flow. As such, a choke valve model can be considered as a simple Virtual Flow Meter because the flow is not measured directly but rather estimated. However, estimating the flow over the choke is not a straightforward task due to the multiphase flow complexity.

![image](https://user-images.githubusercontent.com/29730122/161019046-5cb1d2d6-9af3-41b0-b1ee-440a8127392e.png)



 
