# INSAID_TASK
# Predicting Fraudulent Transactions
# Business Context
This case requires trainees to develop a model for predicting fraudulent transactions for a financial company and use insights from the model to develop an actionable plan. Data for the case is available in CSV format having 6362620 rows and 10 columns.

Candidates can use whatever method they wish to develop their machine learning model. Following usual model development procedures, the model would be estimated on the calibration data and tested on the validation data. This case requires both statistical analysis and creativity/judgment. We recommend you spend time on both fine-tuning and interpreting the results of your machine learning model.

## Data Dictionary & Source Acquisition
### Data Dictionary: The data dictionary of the dataset can be found here.
### Data Source: The dataset can be found here.

## Candidate Expectations

### Your task is to execute the process for proactive detection of fraud while answering following questions.
1. Data cleaning including missing values, outliers and multi-collinearity. 
2. Describe your fraud detection model in elaboration. 
3. How did you select variables to be included in the model?
4. Demonstrate the performance of the model by using best set of tools. 
5. What are the key factors that predict fraudulent customer? 
6. Do these factors make sense? If yes, How? If not, How not? 
7. What kind of prevention should be adopted while company update its infrastructure?
8. Assuming these actions have been implemented, how would you determine if they work

## Importing required packages
## Data cleaning including missing values, outliers and multi-collinearity.
## Here i checked the missing values. Here's no null values and duplicates values.
## Checking outliers
## We can see in this dataset there are many outliers. So we've to cap the data
## Encode the Non Numerical Data
## Here we can see the capped data. there is no outliers.
## Multicolinearity

Multicollinearity refers to the correlation or high interdependence between predictor variables in a regression or machine learning model.

We can see that oldbalanceOrg and newbalanceOrig have too high VIF thus they are highly correlated. Similarly oldbalanceDest and newbalanceDest, also nameDest is connected to nameOrig.

Thus combine these pairs of colinear attributes and drop the individual ones.

## How did you select variables to be included in the model?

Using the VIF values and correlation heatmap. We just need to check if there are any two attributes highly negetively correlated to each other and then drop the one which is less correlated.

## Model Building
## Splitting data

##Baseline Algorithm Checking

---

From the dataset, we will analysis and build a model to predict if a given set of symptoms lead to breast cancer.

This is a binary classification problem, and a few algorithms are appropriate for use.

Since we do not know which one will perform the best at the point, we will do a quick test on the few appropriate algorithms with default setting to get an early indication of how each of them perform.

We will use 10 fold cross validation for each testing.

---



The following linear algorithms will be used, namely:

**Classification and Regression Trees (CART)**

**k-Nearest Neighbors (KNN).**

**Random Forest**

## Here, we have build the Random Forest Classifier model with default parameter of n_estimators = 10

## KNN
## Build the model with k=6

## CONCLUSION

Comparing with all model (Random Forest, Decision Tree and KNN), we can say **Random Forest** is the Higher AUC.

So, we can do with this model.

In a this model, very important is instead of predicting normal transactions correctly we want Fraud transactions to be predicted correctly.

This is also one of the reason why Random Forest are used unstead of other algorithms.

Also the reason chosen this model is because of this is a highly unbalanced dataset.

Normal: Fraud :: 99.87 : 0.13

Random forest makes multiple decision trees which makes it easier (although time taking) for model to understand the data in a simpler way since Decision Tree and KNN makes decisions in a boolean way.

## Describe your fraud detection model in elaboration. 

---

**Model Overview:** The fraud detection model is built using the Random Forest algorithm, which is an ensemble learning method that combines multiple decision trees to make predictions. Random Forest is known for its ability to handle high-dimensional datasets and provide robust performance in various classification tasks, including fraud detection.

**Data Preparation:** The model requires a dataset that consists of labeled examples where each example represents a transaction or an event, and the label indicates whether it is fraudulent or not. The dataset is preprocessed to handle missing values, outliers, and data inconsistencies.

Categorical variables may be encoded using techniques like one-hot encoding or label encoding.

The data is then split into training and testing sets to evaluate the model's performance on unseen data.

### Demonstrate the performance of the model by using best set of tools

**Model Training:** Train a Random Forest classifier using the training dataset. Random Forest is an ensemble learning method that combines multiple decision trees to make predictions. It is known for its ability to handle high-dimensional datasets and provide robust performance.

**Model Evaluation:** Evaluate the trained model using appropriate evaluation metrics such as accuracy, precision, recall, and F1-score. Additionally, consider using techniques like cross-validation to obtain more reliable estimates of the model's performance.

**Testing:** Apply the trained and optimized model on the testing dataset to assess its performance on unseen data. Calculate and report the evaluation metrics to measure the model's effectiveness in detecting fraudulent transactions.

**Monitoring and Refinement:** Continuously monitor the model's performance in real-world scenarios and refine it as needed. This includes periodically retraining the model on updated data and evaluating its performance to ensure its effectiveness in detecting fraud.


### What are the key factors that predict fraudulent customer?

---

1. **Transaction Behavior:**
2. **Geographical Information:**
3. If there is no evidence that the transaction is taking place, then there may be doubts about this as well. 
4. If the background is not available by verifying whether the transaction has been given digital or paper proof, they may be fraudulent customer.
5. Customer Activities: login patterns, multiple failed login attempts, frequent changes to personal information, or suspicious account updates.
6. Relationships between customers can provide insights into fraudulent behavior. Identifying networks of customers involved in fraudulent activities or customers associated with known fraudsters can help identify potential fraud cases.
7. **History of Crime:**
8. **Payment Information:** 

9. **Anomaly Detection:**
10. **Blured ID's, Fake KYC (Know Your Customer)**

## Do these factors make sense? If yes, How? If not, How not?


---

Yes, these factors make sense of predicting fraudulent customers.

1. In an account that has been inactive for a long time, if suddenly there is an excessive amount of transaction or limited money continues to be credited.
2. Even if it is legal, Unusual changes in a customer's location, transactions from multiple geographically distant locations within a short time. it can be seen from the fact that the transaction is taking place beyond the limit.
3. If there is no evidence that the transaction is taking place, then there may be doubts about this as well. 
4. If the background is not available by verifying whether the transaction has been given digital or paper proof, they may be fraudulent customer.
5. Customer Activities: login patterns, multiple failed login attempts, frequent changes to personal information, or suspicious account updates.
6. Relationships between customers can provide insights into fraudulent behavior. Identifying networks of customers involved in fraudulent activities or customers associated with known fraudsters can help identify potential fraud cases.
7. Historical fraud patterns includes identifying specific transaction types or product categories that are frequently associated with fraud, as well as common patterns in the timing or sequencing of fraudulent activities.
8. Unusual payment methods, frequent changes in payment details, multiple accounts associated with the same payment information, or transactions involving stolen or compromised credit card information.

9. Leveraging anomaly detection techniques can help identify outliers or unusual patterns in customer behavior. Unusual purchase patterns, unexpected changes in spending habits, or abnormal transaction sequences can be identified using anomaly detection techniques.

### What kind of prevention should be adopted while company update its infrastructure?

---

1. **Security:** Ensure that security is a fundamental aspect of the architecture, including network design, access controls, data storage, and encryption. 
2. **Access Control and Authentication:** This includes the use of strong passwords and limit access.
3. **Network:** Separating systems and services based on their security requirements, you can minimize the lateral movement of attackers within the network.
4. **Encryption and Protection:** These are sensitive data. Need to properly encrypted in transit. Strong encryption algorithms and protocols to protect data from unauthorized access. We can use Machine Learning Algorithm to monitor and prevent the unauthorized transmission of sensitive data.
5. **Monitoring and Logging:** Monitoring and logging solutions to capture and analyze system logs, network traffic, and security events.
6. **Education and Awareness:** Conduct regular training programs to educate employees about security best practices, such as identifying phishing emails, avoiding suspicious websites, and using secure communication channels. 
7. **Incident Response:** An incident response plan that outlines the steps to be taken in the event of a security incident.
8. **Disaster Recovery:** Backup and disaster recovery mechanisms to ensure business continuity in case of infrastructure failures or security breaches.
9. **Third-Party Risk Management:** Evaluate the security practices and policies of third-party vendors or service providers involved in the infrastructure update. 
10. **Compliance and Regulatory Considerations:** Ensure that the updated infrastructure adheres to relevant industry regulations and compliance standards, Consider privacy requirements and implement necessary controls to protect personal data.

### Assuming these actions have been implemented, how would you determine if they work?


---

**Security Audits:** Conduct periodic security audits to evaluate the implemented security controls and measures. Engage internal or external security experts to review the infrastructure, conduct vulnerability assessments, penetration testing, and analyze the overall security posture.

**Incident Response and Monitoring:** Monitor security incidents and responses is an effectiveness of preventive measures. Such as unauthorized access attempts, data breaches.

**User Feedback and Awareness:** Seek feedback from employees, system administrators, and users regarding their experience with the updated infrastructure and security measures. 
Conduct surveys, interviews, or feedback sessions to gather insights into their perception of the security measures and whether they feel more confident in the system's security.

**Compliance and Audit Reports:** Review compliance reports and audit findings to evaluate adherence to relevant industry regulations and standards.

**Continuous Monitoring:** Implement continuous monitoring of the infrastructure, including real-time log analysis, network traffic monitoring, and threat intelligence feeds. 

**Lessons Learned and Improvement Actions:** Regularly conduct lessons learned sessions or post-incident reviews to identify areas for improvement. Use this information to refine security controls, update policies and procedures, and implement necessary improvements.

By employing these evaluation methods, you can gain insights into the effectiveness of the implemented security measures. It is important to have a proactive and continuous approach to security evaluation, ensuring that preventive measures are regularly reviewed, adjusted, and enhanced to address emerging threats and evolving security challenges.

