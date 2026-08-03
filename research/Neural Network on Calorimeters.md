---
tags:
  - type/exercise
  - context/HEP_Herbstschule2025
  - topic/detector_physics
  - topic/neural_networks
aliases:
date: 2025-09-04
---
Share materials under https://cern.ch/ml-calo-exercise
 [[[CERN box]]](https://cernbox.cern.ch/files/link/public/i5oboZ8Ma0nFJmg?tiles-size=1&items-per-page=100&view-mode=resource-table)
 
 Enter Jupyter Notebook under https://etpwww.etp.kit.edu/~jkiesele/calodnn.html
## **Electromagnetic calorimeters**
- radiation length $$X_0 = \frac{A}{4\alpha N_AZ^2r_e^2\ln\frac{183}{Z^{1/3}}}$$
- **longitudinal** showers 
	- Electron loses 1− 1/_e_ = 63 % of it’s energy in one $X_0$
- radius of the showers the **Moliere radius**

## Investigate the shower profile **The software**

How to detect energy - response and resolution 

- Plot the logarithm and plot the distance in terms of radiation length on the x-axis
- Aim for 30 radiation length
- plot the visible energy devided by the true energy 
- Homogeneous calirometers give you much bettter resolution

## Neural Network
- DNNs and their parameters
- output is always the energy 
- Universal function approximaters 
- Activation function that is not linear 
	- For all the hidden layers, the choise of the activation function it does not really matter 
	- **Choose something that ends with ELU**
	- Beware of extrapolation 
- How good is the approximation? 
- [[Loss, AUC and Accuracy|Loss]] function
- Gradiant descent 
- monitor it yourself
- Momentum helps
Learning rate between $10^{-2} - 10^{-12}$ 
- choose a learning rate that explose and devide by 100 
- Overfitting
Choose a validation data set to avoid overfitting 
- lower learning rtes
- simpler network 
- more data per weight 
- You wont need many parameters
MLP_dataloader 

3 hiddenlayers with 8 nots each 
Energy 1-50GeV 
5000 events to start with 

**Classes, classes inheritance** Vererbung

2 Wochen C++ tutorial - einfach durcharbeiten - 


For hadronic calorimeter -10 to 12 interaction length 
For samling calorimeter - total deposite energy 