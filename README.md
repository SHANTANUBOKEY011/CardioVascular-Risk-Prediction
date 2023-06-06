# CardioVascular-Risk-Prediction

* **Cardiovascular diseases (CVDs) are the major cause of mortality worldwide. According to WHO, 17.9 million people died from CVDs in 2019, accounting for 32% of all global fatalities.**
* Though CVDs cannot be treated, predicting the risk of the disease and taking the necessary precautions and medications can help to avoid severe symptoms and, in some cases, even death.
* As a result, it is critical that we accurately predict the risk of heart disease in order to avert as many fatalities as possible.
* The goal of this project is to develop a classification model that can predict if a patient is at risk of coronary heart disease (CHD) over the period of 10 years, based on demographic, lifestyle, and medical history.
## **We followed the following sequence of steps to achieve this goal:**
* Understanding the dataset, doing some basic inspection on the raw data to check the number of columns, understanding distribution of data and checking statistics of the data in each variable. Checking for and handling missing values, Visualizing the distributions and boxplots of each variable to handle the outliers, Cleaning the data.
* Feature engineering: After getting some insights from the dataset we created some new features, altered the existing features so that they can move forward for the model building phase.
* EDA & Data insight: As mentioned earlier we worked with the heart disease detection dataset and we put out interesting inferences from the data to derive some meaningful results by doing univariate, bivariate and correlation analysis.
* After EDA we to visualize the severity of multicollinearity. Removed multicollinearity based on VIF factor. Scaled the data and started experimenting different algorithms. First, we started with simple models like Logistic Regression and Naïve Bayes algorithm then to enhance the accuracy we tried some complex algorithms too.
* Model building: In this phase, we built our Machine learning model for heart disease detection, evaluated on different metrics compared the results, tuned the hyperparameters of models to get the best performance, we also had a rough idea on feature importance.

# **Summary and Conclusion:**
* **18%(269), 11%(118), 12%(70), 14%(54) of the patients belonging to the education level 1, 2, 3, 4 respectively were eventually diagnosed with CHD.**
* **Male patients have significantly higher risk of CHD 18%(272) than female patients 12%(239)**
* **Patients who smoke have significantly higher risk of CHD 16%(275) than patients who don't smoke 13%(236)**
* **Patients who take BP medicines have significantly higher risk of CHD 33%(33) than other patients 14%(478)**
* **Patients who had experienced a stroke in their life have significantly higher risk of CHD 45%(10) than other patients 14%(501)**
* **Hypertensive patients have significantly higher risk of CHD 23%(255) than other patients 11%(256)**
* **Diabetic patients have significantly higher risk of CHD 37%(33) than other patients 14%(478)**

### **recall score of test dataset:**
* **Logistic Regression: 42(69%)**
* **K nearest neighbors: 40(61%)**
* **Naive bayes: 38(63%)**
* **Decision tree with GridSearchCV: 19(81%)**
* **Support Vector Machine: 23(77%)**
* **Random Forest with GridSearchCV: 0(100%)**
* **XgBoost Classifier: 90(12%)** 
      here we can see that, Decision Tree with GridSearchCV, Support Vector Machine, Random Forest with GridSearchCV gives the best recall score.

Q. why we are using recall score?
* Ans. Since we are dealing with data related to healthcare, False Negatives are of higher concern than False Positives. it doesn’t matter whether we raise a false alarm but the actual positive cases should not go undetected. it is decided that we use Recall as the model evaluation metric.  

### **Important Features:**
**features which predict CVD will occur:**
* total_cholestrol
* heart_rate
* cigs_per_day
* bp_meds
* diabetes
* age 

**features which predict CVD will not occur:**
* education
* sex
* bmi
* prevalent_stroke


- **It is critical that the model we develop has a high recall score.** It is OK if the model incorrectly identifies a healthy patient as a high risk patient because it will not result in death, but if a high risk patient is incorrectly labelled as healthy, it may result in fatality.
- **Future developments must include a strategy to improve the model recall score, enabling us to save even more lives from this disease. This includes involving more people in the study, and include people with different medical history, etc build an application with better recall score.**
- Since we have added synthetic datapoints to handle the huge class imbalance in training set, the data distribution in train and test are different so the **high performance of models in the train set is due to the train-test data distribution mismatch and not due to overfitting.**
