# Telco-churn-prediction-with-Machine Learning Algorithms
As someone passionate about data analysis, I built this project to predict customer churn in a telecom company using Machine Learning algorithms.
The goal is to detect customers likely to leave the company, based on real data (contracts, services, payments, history...), and support retention strategies.
This project highlights my skills in data exploration, predictive modeling, and data visualization.
## Project Pipeline
The script is divided into 6 main steps:
1. 📥 Data Loading
Loading the Telco dataset from a CSV file.
2. 📊 Data Visualization (Exploratory Data Analysis – EDA)
Global overview of the data structure, variable types, missing values, and initial descriptive statistics.
3. 📈 Univariate Data Visualization
Graphical analysis of each variable individually to understand its distribution.
4. 📉 Bivariate Analysis
Study of the relationships between independent variables and the target variable Churn.
5. 🧹 Data Preprocessing
Preparing the data for modeling: encoding categorical variables, normalization, handling missing values, and splitting the data into train/test sets.
6. 🤖 Modeling
Training various classification models and evaluating their performance using metrics such as accuracy, recall, and F1-score.

## Modeling

## Support Vector Classifier for Churn Prediction
The Support Vector Classifier (SVC) is an implementation of Support Vector Machines (SVM) designed specifically for classification tasks, and is available in the scikit-learn library. It is a supervised learning algorithm that aims to find the optimal hyperplane that separates classes while maximizing the margin between them.
In the context of churn prediction, the goal is to identify customers who are likely to cancel a service. SVC is particularly well-suited for this type of problem, as customer data is often multi-dimensional (usage behavior, billing, customer support interactions, etc.) and may involve complex decision boundaries between loyal and at-risk customers.
Thanks to its robustness to noise and flexibility through the use of various kernels, SVC provides an effective approach for modeling churn probability.
## Random Forest for churn prediction 
Random Forest is a supervised learning algorithm based on an ensemble of decision trees. It combines the predictions of multiple trees built on random subsets of the data in order to improve accuracy and reduce the risk of overfitting.
In the context of churn prediction, Random Forest is particularly effective at handling complex and heterogeneous data (such as demographic information, usage history, customer support interactions, etc.). It can capture non-linear relationships between variables and helps rank the most important features for identifying customers at risk of leaving.
Thanks to its robustness and strong generalization ability, Random Forest is a powerful solution for detecting at-risk behavior within customer databases.
## GaussianNB for churn prediction 
Gaussian Naive Bayes is a supervised classification algorithm based on Bayes' theorem, assuming that the features are independent of each other and follow a Gaussian (normal) distribution. It is particularly valued for its simplicity, fast training time, and ability to perform well even with small datasets.
In the context of churn prediction, GaussianNB can be used to identify customers at risk of leaving based on their past behavior.

## Result
* SVC model
The evaluation of the SVC model on the test set resulted in an accuracy of 79%, indicating an overall satisfactory performance. The model performs well on the non-churn class, with a precision of 0.83 and a recall of 0.91.
However, the performance on the churn class is weaker, with a recall of 0.47 and an F1-score of 0.55, suggesting that the model struggles to accurately identify customers who are likely to churn. This may be due to class imbalance or the model’s limited capacity to capture the complex patterns associated with churn behavior.
* Random Forest 
The evaluation of the Random Forest model yielded an accuracy of 78%, indicating an overall good performance on the test set. The model is effective at classifying non-churners, with a precision of 82% and a recall of 90%, meaning it accurately identifies most loyal customers.
However, performance on the churn class (customers at risk of leaving) is weaker:
Precision: 62%
Recall: 45%
F1-score: 52%
These results suggest that the model has more difficulty identifying customers likely to churn, which may be due to a class imbalance (fewer churners in the data). To improve detection of this class, data balancing techniques or hyperparameter optimization could be considered.
* GuassianNB 
The Gaussian Naive Bayes model achieved an overall accuracy of 74%, reflecting a moderate performance on the test set. Despite its simplicity, it stands out for maintaining a good balance in detecting both classes.
For the non-churn class (loyal customers), the model achieved a precision of 88% and a recall of 74%, indicating that it correctly identifies most of the customers who stay.
For the churn class (at-risk customers), it shows a precision of 51% but a high recall of 73%, meaning it successfully detects a large portion of customers likely to churn, though at the cost of some false positives.
This behavior — high recall on churners — is often desirable in churn prediction scenarios, as it is generally preferable to identify as many at-risk customers as possible, even if it includes some false positives.
* Comparative Table

| Model             | Class         | Precision | Recall | F1-score | Accuracy |
| ----------------- | ------------- | --------- | ------ | -------- | -------- |
| **SVC**           | 0 (non-churn) | 0.83      | 0.91   | 0.87     | **0.79** |
|                   | 1 (churn)     | 0.66      | 0.47   | 0.55     |          |
| **Random Forest** | 0 (non-churn) | 0.82      | 0.90   | 0.86     | **0.78** |
|                   | 1 (churn)     | 0.62      | 0.45   | 0.52     |          |
| **GaussianNB**    | 0 (non-churn) | 0.88      | 0.74   | 0.81     | **0.74** |
|                   | 1 (churn)     | 0.51      | 0.73   | 0.60     |          |

 * Comparative Analysis
 ✅ SVC (Support Vector Classifier)
Best overall accuracy (79%)
Excellent performance on non-churners
Low recall on churners (47%), meaning many at-risk customers are missed
Less effective for critical churn detection tasks
✅ Random Forest
Performance very close to SVC
Good balance of precision and recall for the non-churn class
Recall still low for churners (45%), showing the same limitation as SVC
✅ Gaussian Naive Bayes
Lower overall accuracy (74%), but:
Highest recall on churners (73%), which is valuable in a business context
Can detect more at-risk customers, even if it sacrifices some precision








