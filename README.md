# Analyzing Correlated Data Using Logistic Regression Models

One assumption of logistic regssion is that all observations are independent of one another. Sometimes, this assumption is broken. This can happen when observations are repeated measures, or when observations are grouped by a certain factor (e.g. neighborhoods, hospitals). 
This data analysis project uses two methods (**generalized estimating equations and random effects models**) to fit models on such correlated data using an example data set of a longitudinal MRI study.

**A Longitudinal MRI Study** (https://www.kaggle.com/jboysen/mri-and-alzheimers#oasis_longitudinal.csv)

The data set contains information from a longitudinal MRI study done on 150 patients with and without dementia. Each patient was scanned during two or more visits, where visits were at least one year apart. The data was made available by the Open Access Series of Imaging Studies (OASIS) project and accessed on Kaggle. The data contains patients’ demographic and anatomic information. Speciﬁcally, the data set has 373 observations with the following features:

* Subject ID 
* Visit Number 
* Gender 
* Age 
* Years of education 
* Whether or not the patient’s group status changed at any point during the time of the study (group statuses are demented or not demented) 
* Clinical Dementia Rating (CDR) 
* Estimated total intracranial volume in mm3 (eTIV) 
* Normalized whole brain volume (nWBV) 

The CDR has the following possible scores: 0 (no dementia), 0.5 (very mild dementia), 1 (mild dementia), 2 (moderate dementia), and 3 (severe dementia). Thus, I will convert this feature into a binary outcome variable so that a CDR score of 0 is no dementia (Class = 0) and any score above 0 is dementia (Class = 1). 

As this data set has correlated observations (groups are subjects), **the goal of this project will be to perform a GEE analysis and random eﬀects modeling analysis to predict whether or not a patient as dementia. Specifically, the analysis will focus on conducting variable and correlation structure selection for GEE, and on choosing fixed/random effects for random effects analysis.** 

Note: In order to make the variables on similar scales so that model coeﬃcients are of similar magnitude, eTIV was divided by 1000 (units are now in cm3), nWBV was multipled by 10, and age was divided by 10.

For more on the methods, see:  
Hosmer, D.W., Jr., Lemeshow, S. and Sturdivant, R.X. (2013). Logistic Regression Models for the Analysis of Correlated Data. In *Applied Logistic Regression* (eds D.W. Hosmer, S. Lemeshow and R.X. Sturdivant).
