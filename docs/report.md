# H1-B Visa Prediction Model


The H-1B program applies to employers seeking to hire nonimmigrant aliens as workers in specialty occupations or as fashion models of distinguished merit and ability. A specialty occupation is one that requires the application of a body of highly specialized knowledge and the attainment of at least a bachelor’s degree or its equivalent. The intent of the H-1B provisions is to help employers who cannot otherwise obtain needed business skills and abilities from the U.S. workforce by authorizing the temporary employment of qualified individuals who are not otherwise authorized to work in the United States.

H1-B Visa Prediction looks interesting to understand and predict as an international student. More than 80,000 foreign nationals receive H-1B Visa every year. The selection process for H-1B Visa is highly competitive. I always heard about H1-B Visa approval from distant cousins and friends who are working in USA. Unlike other visa types where you can apply for yourself, the H-1B visa requires your employer to apply on your behalf. 
I would like to understand what features play crucial role in the acceptance of H1-B Visa and predict with good accuracy score generating models. In this project, we aim to develop a predictive model using machine learning algorithms to determine the likelihood of receiving an H1B visa. The model will be trained on a comprehensive dataset of past H1B visa applications and tested on a set of validation data to evaluate its accuracy. The results of this analysis can provide insights into the factors that influence H1B visa outcomes and assist employers and visa applicants in making informed decisions.


## Data set
Dataset has data based on 6 year H1-B application data.
* It has 3002458 rows and 11 columns
* Columns used are:
CASE_STATUS (Target Column), EMPLOYER_NAME, SOC_NAME, JOB_TITLE, FULL_TIME_POSITION, PREVAILING_WAGE, YEAR, WORKSITE, lon, lat  



## Feature columns and Target Variable
The feature columns which I have considered for EDA and predication are related to the Job roles, employer information and Wages.
Target variable would be the Case Status which has the values Certified, Certified - Withdrawn, Denied and Withdrawn.
* Certified – Withdrawn : This can be updated to Certified because It was certified by DOL, but employer choose not to use it to file H1B petition,
so they withdrew the LCA. It cannot be used for filing H1B petition anymore. 
* Withdrawn : It means that employer withdrew the LCA application before the decision was made by DOL. We don't need this data and this data will be eliminated.
## Removing Outliers
Method Used:  Z-score

* Before applying : 0.9679485418826776
* After Applying: 0.9685945068204025

* There is increase of approximately 0.001% accuracy with Logistic Regression
* Data is highly imbalanced

* Initial Confusion Matrix:
array([[    42,  18064],
       [     0, 557080]], dtype=int64)
* Later Confusion Matrix:
array([[ 26376, 537496],
       [  5163, 558283]], dtype=int64)

* After Upsampling:
      
               precision    recall  f1-score   support

           0       0.84      0.05      0.09    563872
           1       0.51      0.99      0.67    563446


## ML Methodologies
Please find the applied models below and its accuracies.
### Logistic Regression:

Logistic regression is a statistical modeling technique used for predicting binary outcomes, making it a suitable approach for H1B visa prediction analysis. The logistic regression model estimates the probability of the occurrence of a binary event based on one or more predictor variables. In the case of H1B visa prediction analysis, logistic regression can be used to predict the likelihood of an applicant getting approval or denial for their visa application based on various factors such as education level, job title, employer information, and more. Logistic regression can also be used to identify which factors have a stronger influence on visa outcomes and to develop models for making predictions based on historical data. Overall, logistic regression can be a powerful tool for H1B visa prediction analysis, helping organizations make informed decisions about their visa application process.
**Accuracy:** 52%
### Decision Tree Classifier:
Decision Tree Classifier is a popular machine learning algorithm that is used in h1b prediction analysis. It works by creating a decision tree to model the relationships between the various features of the dataset, and then using this tree to make predictions about new instances. The tree is built by recursively splitting the data into smaller and smaller subsets based on the values of the features, until each subset contains instances that belong to a single class. The algorithm selects the best feature to split on at each node based on a certain criterion, such as information gain or Gini impurity.

One of the advantages of Decision Tree Classifier is its interpretability. The tree can be visualized and easily understood by non-technical stakeholders. Additionally, the algorithm can handle both categorical and continuous features and is robust to outliers. However, it is prone to overfitting and can be unstable, particularly with small datasets. Techniques such as pruning, ensembling, and setting a minimum number of instances per leaf can be used to address these issues. Overall, Decision Tree Classifier is a useful algorithm for h1b prediction analysis, particularly when combined with other techniques such as feature selection and ensemble methods.

**Accuracy:** 81%

### Gradient Boosting Classifier:
Gradient Boosting Classifier is a popular machine learning algorithm used in h1b prediction analysis due to its ability to handle complex datasets with high accuracy. The algorithm works by combining weak learners, typically decision trees, to form a strong learner. Each subsequent weak learner is trained on the residual errors of the previous learner until the desired accuracy is achieved.

The algorithm has several hyperparameters that can be fine-tuned to optimize its performance, such as the number of trees, learning rate, and maximum depth. By optimizing these hyperparameters, Gradient Boosting Classifier can achieve high accuracy and can handle both numerical and categorical features.

One potential limitation of Gradient Boosting Classifier is that it can be computationally expensive, especially with a large dataset or when using a deep decision tree. However, the algorithm is widely used in h1b prediction analysis due to its ability to handle complex datasets with high accuracy.
**Accuracy:** 68%

### Random Forest:
Random Forest is a popular ensemble learning technique used for classification problems, including H1B prediction analysis. It works by constructing multiple decision trees on different sub-samples of the data and averaging the results of those trees to obtain a final prediction.

In H1B prediction analysis, a random forest model is trained using a set of features that are likely to influence the H1B visa approval or denial decision. These features include job title, salary, education, work experience, location, and more.

Random Forest has the advantage of reducing overfitting and increasing the accuracy of the model by creating a diverse set of decision trees. Additionally, it can handle missing values, and feature selection is not required. It is also scalable and can handle large datasets with high dimensionality.

However, random forest has some limitations, including the risk of overfitting when the number of trees is too high, and the model's interpretability may be limited. Nonetheless, the random forest algorithm is a powerful technique for H1B prediction analysis, and it has been shown to achieve high prediction accuracy.
**Accuracy:** 81%

### K Nearest Neighbors (KNN):
K Nearest Neighbors (KNN) is a supervised machine learning algorithm that can be used for classification and regression problems. In the context of H1B visa prediction analysis, KNN can be applied to classify whether an application is likely to be certified or denied based on its features such as job title, employer, wage rate, etc.

KNN works by identifying the K closest data points to the given input data point and then assigning a label to the input based on the most common label among the K nearest neighbors. The value of K can be chosen based on the size of the dataset and the complexity of the problem.

One advantage of KNN is that it is a non-parametric algorithm and does not make any assumptions about the distribution of the data. Additionally, it can work well with large datasets and can be easily extended to handle multi-class classification problems.

However, KNN can be sensitive to the choice of distance metric and the number of neighbors K. Also, it can be computationally expensive to calculate distances between the input and all data points in the dataset. Therefore, it may not be the best choice for high-dimensional data with many features.
**Accuracy:** 77%
### AdaBoost Classifier
Adaboost is a popular machine learning algorithm used for classification tasks, including H1B visa prediction analysis. It is an ensemble learning method that combines multiple "weak" classifiers to create a "strong" classifier. In the case of H1B prediction analysis, Adaboost could be used to combine decision trees or other classifiers to improve the accuracy of the predictions.

Adaboost works by assigning weights to each training example and focusing on the examples that the weak classifiers are not accurately classifying. It trains multiple classifiers on subsets of the data, and then combines them into a final model by weighting their individual predictions. The final model is optimized to minimize the overall error of the combined classifiers.

Adaboost has several advantages, including being easy to implement, handling large datasets well, and being able to handle a wide range of input features. However, it can be sensitive to noisy data and outliers, and it can be computationally expensive when dealing with large datasets or complex models. Overall, Adaboost can be a useful tool for H1B prediction analysis, particularly when combined with other classifiers in an ensemble learning approach.
**Accuracy:** 68%
### XGBoost Classifier
XGBoost (Extreme Gradient Boosting) is a type of decision tree ensemble model that has gained popularity in recent years due to its ability to handle large and complex datasets. XGBoost is an extension of the Gradient Boosting method and works by iteratively adding decision trees to the model while adjusting the weights of the samples to minimize the loss function.

In the context of H1B prediction analysis, XGBoost can be used to predict the likelihood of an H1B application being approved or denied based on various features such as job title, location, employer, education, etc. XGBoost can handle both categorical and numerical features and is capable of capturing complex interactions between them.

XGBoost also has several hyperparameters that can be tuned to improve its performance such as the number of trees, learning rate, maximum depth of the trees, regularization parameters, and more. Additionally, XGBoost provides a feature importance score, which can be used to understand which features are most influential in the prediction model.

Overall, XGBoost is a powerful machine learning algorithm that can be used for H1B prediction analysis and has proven to be effective in several real-world scenarios.

**Accuracy:** 69%
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

https://github.com/akukudala/Akshitha_Data606/blob/main/docs/capstone.pptx
## Youtube Explaination:

https://www.youtube.com/watch?v=--sLhkICtLw
