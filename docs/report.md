# H1-B Visa Prediction Model


The H-1B program applies to employers seeking to hire nonimmigrant aliens as workers in specialty occupations or as fashion models of distinguished merit and ability. A specialty occupation is one that requires the application of a body of highly specialized knowledge and the attainment of at least a bachelor’s degree or its equivalent. The intent of the H-1B provisions is to help employers who cannot otherwise obtain needed business skills and abilities from the U.S. workforce by authorizing the temporary employment of qualified individuals who are not otherwise authorized to work in the United States.

H1-B Visa Prediction looks interesting to understand and predict as an international student. More than 80,000 foreign nationals receive H-1B Visa every year. The selection process for H-1B Visa is highly competitive. The denial rates have constantly increased from 6% in 2015 to about 21% in 2020. I always heard about H1-B Visa approval from distant cousins and friends who are working in USA. Unlike other visa types where you can apply for yourself, the H-1B visa requires your employer to apply on your behalf. 
I would like to understand what features play crucial role in the acceptance of H1-B Visa and predict with good accuracy score generating models.

## Data set
Datasets considered in this project belong to 2017, 2018, 2019 years of H1-B applications.
Data sets used in this project are taken from https://www.dol.gov/agencies/eta/foreign-labor/performance <br/>
File Names: <br/>
* H-1B FY2019.xlsx
* H-1B FY2018.xlsx
* H-1B FY2017.xlsx <br/>
Size of the each dataset is 270MB.
There are around 260 columns in each Dataset with the combination of object and Datatime columns. After cleaning the data,
I am planning to use only 10 columns from the existing 260 columns and then concatinate the three dataframes. 

## Feature columns and Target Variable
The feature columns which I am going to consider for EDA and predication are related to the Job experience, Job roles, employer information and Wages.
Target variable would be the Case Status which has the values Certified, Certified - Withdrawn, Denied and Withdrawn.
* Certified – Withdrawn : This can be updated to Certified because It was certified by DOL, but employer choose not to use it to file H1B petition,
so they withdrew the LCA. It cannot be used for filing H1B petition anymore. 
* Withdrawn : It means that employer withdrew the LCA application before the decision was made by DOL. We don't need this data and this data will be eliminated.

## ML Methodologies
I would like to apply Logistic Regression, SVM and Neural Network techniques for this application. Might include any other ML models if required. 


## Questions for EDA and Modeling.
* Analysis will be done on which employer has the most applicants.
* Which role has more acceptance or rejections?
* Year wise observation of applications and employers.
* Which of the given features play important role in the acceptance of the lottery system of H1-B?
* How does the wage effect the Case status?
* Which Employer state or city has most acceptance rate year wise?

## What do you want to achieve in this project?
I would like to complete this project by implementing my skills learnt from the courses I have taken in this Data Science course. I will try to implement and explain different models and find the accuracy to determine the best model.
Using the real time data to predict the real time values based on the learnt techniques is doing to be interesting.
## Presentation Link
## Youtube Explaination:

https://www.youtube.com/watch?v=--sLhkICtLw
