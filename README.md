# Improved Predictive Models for Acute Kidney Injury with IDEAs: Intraoperative Data Embedded Analytics

## Introduction
Acute kidney injury (AKI) − an abrupt loss of kidney function − is a common and serious complication after a surgery which is associated with a high incidence of morbidity and mortality. The majority of existing perioperative AKI risk score prediction models are limited in their generalizability and do not fully utilize the physiological intraoperative time-series data. Thus, there is a need for intelligent, accurate, and robust systems, able to leverage information from large-scale data to predict patient’s risk of developing postoperative AKI. Here, we proposed an intelligent machine learning model that is able to improve patients’ postoperative AKI risk score by taking the intraoperative features into account. 

## High level view of the MySurgeryRisk IDEA algorithm. 

All the available electronic health care data including vital signs from preoperative and intraoperative layers flow into the IDEA machine learning algorithm to preform acute kidney injury (AKI) predictions:

![Alt text](./Images/image0.png?raw=true "High level view of the MySurgeryRisk IDEA algorithm")

## The conceptual diagram of the intraoperative data integrated AKI prediction model. 
This diagram shows the aggregation of data transformer, data engineering, and data analytics modules in preoperative and intraoperative layers. In particular, the two layers can be integrated in two different ways: (1) Stacked preoperative prediction scores with the cleaned and feature engineered intraoperative data, (2) obtain full perioperative dataset by merging all clean features from both layers:

![Alt text](./Images/image1.png?raw=true "The conceptual diagram of the intraoperative data integrated AKI prediction model")

# Random forest model training
The flow diagram of the random forest model used to train and test the perioperative data (e.g., preoperative prediction score stacked with intraoperative features) along with three different AKI outcomes: AKI-3day, AKI-7day, and AKI-Overall. The cohort of size 2,911 with 231 features were randomly split in to 70% train and 30% test cohorts. A random forest classifier was used to train the AKI predication model (we used 5-fold CV for hyper parameter tuning and feature selection) for all three outcomes separately and performance were tested using the testing (validation) cohort:

![Alt text](./Images/image2.png?raw=true "The flow diagram for Random forest model training")

# Results

Physiologic time series variations stratified by AKI-7day outcome for 100 randomly selected patients during the first 200min of the surgery. (A) Average of the mean arterial blood pressure including 95% CI for AKI and no AKI, (B) average of the heart rate values including 95% CI for AKI and no AKI, (C) average of the MAC values including 95% CI for AKI and no AKI: 

![Alt text](./Images/image3.png?raw=true "Physiologic time series variations stratified by AKI-7day outcome")

Receiver-operating characteristic curves and performance metrics for (1) preoperative model, (2) postoperative stacked model, and (3) postoperative full model in predicting AKI-7day outcome from the validation cohort:

![Alt text](./Images/image4.jpg?raw=true "Receiver-operating characteristic curves")

The IDEAs algorithm and results are explained in detail in the following manuscript

* Adhikari L, Ozrazgat-Baslanti T, Ruppert M, Madushani RW, Paliwal S, Hashemighouchani H, Zheng F, Tao M, Lopes JM, Li X, Rashidi P. Improved predictive models for acute kidney injury with IDEA: Intraoperative Data Embedded Analytics. PloS one. 2019 Apr 4;14(4):e0214904. [https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0214904](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0214904).

# Repository content:

* Data preprocessing: This folder contains codes to clean and preprocess time-series data, labs, and medications. 
* IDEA models: This folder contains codes to train Random Forest classifiers (one for each AKI outcome) for perioperative data.
* PreOP models: This folder contains codes to train Generalized Additive Models (GAM) for preoperative data (for comparison purposes). 
* Images: This folder contains few images for the ReadMe file. 

