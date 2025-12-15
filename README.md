# Detecting Money Laundering Suspicious Transactions Using Machine Learning Algorithms
Click on link below to view project in Github

[PROJECT 1: DETECTING MONEY LAUNDERING SUSPICIOUS TRANSACTIONS USING MACHINE LEARNING ALGORITHMS (Random Forest, SVM and Logistic Regression)](https://github.com/PatienceMutede/Detecting-Money-Laundering-using-Machine-Learning/blob/main/Detecting_Money_Laundering_Transactions_using_Machine_Learning_Algorithms.ipynb)


## **The aim of the project is to identify a more accurate machine learning algorithm that effectively provides accurate alerts of suspicious transactions.**

It is crucial for a business to identify and understand its financial crime risks and apply appropriate control to its systems. A firm can effectively identify, mitigate, and discourage financial crime through the implementation of robust systems and controls. There are several methods currently used to detect money laundering, these include Rule based systems and Machine learning algorithms. Most banks and financial institutions use Rule based systems to detect and identify concealed observations from any normal activities, but however this has a lot of limitations. Using machine learning algorithms can be better and more efficient than using rule-based systems. 

**Motivation**

The rapid advancement of technology and global communication has led to a significant increase in fraud, causing financial losses to businesses. Despite the increasing financial crime rates, there has been an increase in the availability of data and big data technologies which has made it easier to uncover insights from data using different machine learning algorithms. There is a significant need for banks to maximise and harness the availability of data to establish robust systems and effective controls for anti-money laundering using advanced analytical techniques. 

**The Problem in the Financial Crime field**

Money Laundering is a major issue that negatively affects economies, financial institutions, and society at large. Most financial institutions use traditional methods to detect money laundering which involve manual effort which often give a lot of errors. Traditional efforts are based on fixed rules. The limitation with the rule-based system is that the rules must be changed with frequent change in data, and it becomes challenging to integrate changes of rules in the systems which affect the results of the frameworks. Additionally, assessing the performance of a rule-based frameworks is challenging, since each rule must be evaluated individually, which is time consuming. The traditional methods are limited to yes or no outcomes and fail to capture interaction between features. 


## **Solution and Strategy I considered**

•	To model machine learning algorithms that can detect potential suspicious money laundering transactions.

•	To identify the most important features in detecting suspicious transactions.

**Approach Used**

This project made use of a Quantitative Research Design. The Design Science Research (DSR) Methodology Process is employed in this project. The relevance of this approach is that it is user centred and first understands the user needs by identifying the problem and showing the importance of the problem. It allows approaching the problem from different angles, supports innovation and creativity. Lastly this research design is most relevant for this research because it reduces risks by first allowing testing and iterative process before implementing the model.

## **Understanding the Dataset**

•  **Class Imbalance**:The dataset is extremely skewed, it contains over 5 million transactions, but only 5,177 are suspicious, resulting in a highly imbalanced ratio (0.001). Undersampling and oversampling are common solutions; this research uses undersampling.

•	  **Data Processing**:Data is cleaned to remove missing values and errors, distribution plots are used to detect outliers, and resampling is applied to handle imbalance. Categorical variables are label-encoded, and features are standardized using SciKit-Learn to ensure consistent scaling.

•	  **Feature Engineering**:A correlation matrix is used in this project to select the most relevant features and remove unnecessary ones.

•	 **Labelling**:All transactions are pre-labelled as suspicious or non-suspicious based on expert classification.

•  **Model Training**:Data is split into training and testing sets. Three supervised machine learning algorithms were used in this project: Random Forest, SVM, and Logistic Regression.

•	 **Model Evaluation**:Models are assessed using confusion matrix and classification metrics such as accuracy, precision, recall, and F1-score. If performance is poor, parameter tuning and feature adjustments are performed.

•	 **Deployment**:The trained and evaluated model will then be deployed in different systems, leveraging the acquired patterns to detect possible illicit transactions.

•	 **Monitoring and Evaluation**The model undergoes is on continuous development and monitoring.

 **Data Processing and Transformation results**

One of the limitations wasclass imbalance: 5 073 168 non suspicious vs 5 177 suspcious. Despite this challenge, resampling is applied to the dataset with the aim of creating a balanced class of data. To address this, all suspicious records were retained and combined with 8,000 randomly selected non-suspicious ones. After undersampling, the dataset contains 13,177 balanced transactions across 11 features. Figure below shows the class distributions. The left side bar graph shows the class distribution of dataset before resampling and the right-hand side shows the class distribution after resampling.

 ![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/class%20dist.png) ![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/Class%20distributions.png)   


For data exploration, the descriptive statistics ofand visualisations were used to understand the distribution of the data and identify relationships between variables. Understanding all the data types in the dataset is very important. It is very important to understand the amount transacted in detecting suspicious transactions

In this project, amount paid, and amount received are equal. This means that the exact amount paid is the exact amount received. Total count of the amount paid is 13177, the average amount of the transactions is 1.4 million. The minimum is very small amount of 0.0032 and maximum a very huge amount of 84 billion. Standard deviation is 957 million, the standard deviation is high showing that the data points are spread over a wide range, and they are not close to the mean. To further investigate how the data points of the amount paid and amount received are distributed, Figure below shows a distribution plot and a box plot of the data points of amount paid and amount received respectively.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/Amount%20Paid%20Distribution.png)

As shown in Figure  above, the distribution of the amount paid, and amount received shows that it is not evenly distributed. The skewness and the kurtosis are greater than 1. The data is right skewed, with the amount paid ranging from 0.003227 up to maximum of 84 billion paid. The Average amount paid in the transactions is 14,974,880.
Our tails are starting from approximately 15 million, this indicates that most of the transactions have small amounts, and a few transactions have very big amounts with maximum amount reaching up to 84 billion. Based on this result, it is concluded that dataset used has outliers of transaction amounts. Therefore, before model building, handling outliers is crucial. Log transformations and robust statistical methods can be used however since the dataset is not balanced the outliers might be very useful transaction in detecting money laundering.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/Payment%20currency%20Histo.png)

Figure Above shows the descriptive statistics of the categorical variables. The most used Payment Currency is US Dollar followed by Euro, Reinvestment is the most used Payment Format, and the most used Receiving Currency is the US Dollar.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/is%20laundering%20vs%20amount.png)

Figure above compares the amount paid to our target variable. Is Laundering being our target variable and 0 is for non-suspicious money laundering transactions and 1 suspicious is for suspicious money laundering transactions. The amount paid for non-suspicious transactions is ranging up to 15 million. It is very interesting to note that the suspicious transactions amount paid is ranging up to 85 billion, which means that the outliers identified in figure 4.2 belong to the suspicious transaction class. This explains that the outliers are suspicious transactions, therefore they must be kept for model training.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/correlation%20matrix.png)

Figure  above shows the correlation between variables. In this research the correlation to be mainly considered is between the target variable and the independent variables. Our target variable is (Is Laundering) which has 2 binary outcomes (Suspicious and Non-Suspicious). From the correlation matrix, it is seen that strong positive and negative correlations exist between some of the variables in our data. The strongest positive correlation is found for:  Is Laundering and Time which is 0.81 • moderate positive correlation between Is Laundering and Account.1 which is 0.68. There is strong negative correlation between Is Laundering and the Payment Format which is -0.86 and moderate negative correlation between Is Laundering and Receiving Currency and Is Laundering and Payment Currency. Overall, the correlation matrix suggests that there is no correlation between Is Laundering and amount paid and received. The Correlation matrix suggests that amount paid, and amount received is not significant in predicting whether a transaction is suspicious or not. It suggests that Timestamp is very important in predicting whether a transaction is suspicious or not. This shows that there is need to consider and focus on the time transactions occur. The negative correlation between Is laundering and the payment format suggests that the more frequent a particular payment format is used the less suspicious the transaction will be for the transaction using that payment format, same applies for receiving currency, the more frequent the receiving currency appeared, the less suspicious.

## Model Performance

**Random Forest Results**

The accuracy of the Random Forest in predicting suspicious money laundering transactions is 0.998. Hyperparameter tuning was done but it did not improve how the model performs. The performance metrics still did not change after hyperparameter tuning. Figure 4.6 below shows the confusion Matrix for the Random Forest Model. Number of True Positives (TP) is 1046 and False Positives is 0, meaning that the technique is good at detecting suspicious transactions because 0 transactions are detected as false positives. False Negatives detected are 3 transactions which is also not bad and True Negatives total is 1537, meaning that the there is no non-suspicious transaction that is detected as suspicious by the Random Forest model. Overall, the model predicts 99%, 1046 suspicious transactions out of a total 1049 suspicious transactions.
Classification report shows that the accuracy of the model is 0.998 close to 1. The model is overall good at all the performance metrics, the precision, recall and F1-score.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/RF%20Confusion%20matrix.png)

**Logistic Regression Results**

The accuracy of the Logistic Regression in predicting suspicious money laundering transactions is 0.64. Figure 4.7 below shows the confusion Matrix for the Logistic Regression Model. Number of True Positives (TP) is 1049 and False Negatives is 0, meaning that the model is very good at detecting all actual suspicious money laundering transactions because 100% of the suspicious transactions were correctly detected. 957 transactions are detected as false positives. True Negatives total is 630. Having a look at number of False Negatives this means that there is no suspicious transaction that is detected as non-suspicious, and this shows the model is good at identifying all suspicious transactions. Overall, the model predicts 1049 suspicious transactions out of a total 1049 suspicious transactions, True Positive detection is at 100%.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/log%20reg%20cnf%20matrix.png)

Classification report shows that the accuracy of the model is 0.64. Precision for non-suspicious transactions is 1 and for Suspicious transactions is 0.52. The Recall for suspicious transactions is 1 and the recall for non-suspicious transactions is 0.4. The model is overall good for classifying suspicious transactions with F1-Score of 0.69.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/table%20class%201.png)

**SVM Results**

The accuracy of the SVM in predicting suspicious money laundering transactions is 0.81. Figure  below presents the Confusion Matrix for SVM Model. Number of True Positives (TP) is 949 and False Positives is 405. False Negatives detected are 100 and True Negatives total is 1182. Having a look at number of 100 False Negatives detected this shows that 0.09% of suspicious transactions were not detected. Generally, this technique is best at minimising false negatives.  The model is not very good at minimising false positives because 25% of the non-suspicious transactions are detected as suspicious. Out of all the actual suspicious transactions 90% were correctly detected as suspicious.  

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/table%20class%202.png)

Classification report shows that the accuracy of the SVM model is 0.81. Precision for non-suspicious transactions is 0.92 and for suspicious transactions is 0,70. The Recall for suspicious transactions is 0.90 and the recall for non-suspicious transactions is 0.74. The model is overall good for classifying suspicious transactions with F1-Score of 0.82 and 0.79 for non-suspicious and suspicious transactions respectively.


![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/findings%20and%20discussions.png)

Comparing the techniques used in this research, Random Forest performs better than the SVM and the Logistic Regression. Random Forest has an accuracy of 0.99, compared to SVM it outperformed SVM by 0.18. SVM also performs well with accuracy score of 0.81. Out of the other models, Logistic Regression has the lowest performance of 0.63 accuracy score.
Based on precision Random Forest has a high score of 0.99, this implies that the model can correctly identify the suspicious transactions. SVM is ranked as second with 0.81 Precision score. Logistic Regression has the lowest Precision score of 0.76. In comparison, based on precision, SVM underperforms the Random Forest by 0.18, which practically is considered non-significant. SVM outperforms Logistic Regression by 0.05 which is a very small difference. Comparing the Accuracy and Precision scores the ranking of the model does not change, Random Forest still outperforms the rest of the techniques.
Based on Recall score Random Forest has the best score of 0.99, this implies that the model can correctly identify the positive suspicious instances and minimise the false negatives. SVM is again ranked as second with 0.82 Recall score. Logistic Regression has the lowest Recall score of 0.70. Comparing the Accuracy and Precision scores the ranking of the model did not change, Random Forest still outperforms the rest of the techniques. In conclusion the Random Forest rarely misses the transactions that are suspicious.
It is very important to note for all the performance metrics of the machine learning techniques per each technique, the accuracy score is higher for Random Forest. For the SVM the higher performance metric is the recall with 0.82 which is higher than its accuracy score of 0.81 which is not much of a difference. The higher performance metric for Logistic Regression is the precision with 0.76, which is higher than its accuracy score of 0.63. This implies that for each technique highest performance metric is not always the accuracy. Other metrics, recall and precision score are very important metrics to also consider for model evaluation.

## **Project Impact**


The above project has been implemented and has improved performance of a Financial Institution. The machine learning algorithms, particularly Random Forest, have significantly improved the business’s anti-money-laundering capabilities. With high recall (0.99) and precision (0.99), Random Forest effectively identifies nearly all suspicious transactions while minimizing false positives, leading to an increase in the number of accurate Suspicious Activity Reports. This allows compliance teams to focus on genuinely high-risk cases, reducing manual workload and improving efficiency. Additionally, the models support enhanced risk-based profiling during client onboarding, accurately flagging potentially high-risk new clients and preventing them from being approved. Overall, the algorithms strengthen detection, improve regulatory compliance, reduce exposure to financial crime, and enhance operational decision-making.

![](https://github.com/PatienceMutede/PatienceMutede_Portfolio/raw/main/Images/AML.png)


As shown on the AML(Anti-Money Laundering) report above. Particularly Random Forest provided meaningful benefits to the organisation's AML anti-money-laundering. As shown on the report above there was an increase in Suspicious Reports, since the model achieved high scores in preicsion and recall, the models can accurately detect suspicious activity with fewer false negatives.

**How the algorithms helped**


**1. Increase in Suspicious Reports** -
A higher Recall means more suspicious transactions identified, Random Forest = **0.99** and SVM recall= **0.82**
High recall means the models captured almost all suspicious transactions, leading to a higher number Suspicious Activity Reports (SARs) being generated, this has improved compliance and reduced crime exposure.

**2. Decrease in High-Risk New Clients** -
Improved precision meansfewer false positives, Random Forest = **0.99** and SVM recall= **0.82**.
High precision means the model is very accurate when it labels a transaction. This helps the business avoid incorrectly tagging legitmate new clients as high risk.
It also helped in better onboarding screening, which has helped clients to identify and block genuinely high risk applicants earlier.
