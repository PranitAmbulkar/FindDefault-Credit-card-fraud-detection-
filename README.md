# FindDefault-Credit-card-fraud-detection

## Problem Statement
A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash.
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. 
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.
We have to build a classification model to predict whether a transaction is fraudulent or not.

- Notebook folder includes the ipynb notebook including Exploratory data analysis and model building.
- visuals folder includes the graphs and visualizations about the data
- data includes the dataset for the model
- model folder includes the .pkl file
- FindDefault_Report is the detailed report about the machine learning model building process in the report format.




## Data Exploration
To protect the user's identity and the security of their confidential information, the dataset 
provider has applied Principal Component Analysis transformation on the original numerical 
features and compressed it into 28 principals components

Only two features have not been transformed i.e. 1) Time and 2) Amount
The feature class will be target column with user labels as:
0 : non-fraudulent 1 : fraudulent

We will get the information about the columns in the DataFrame we have 
created as :
The dataset exclusively comprises numerical features, and notably, there are 
no instances of missing values. Consequently, there is no need for null-value 
handling in this dataset.

We can observe that the genuine transactions are over 99%.
• We will apply scaling techniques on the "Amount" feature to transform the range of values.
• We will drop the original "Amount" column and add a new column with the scaled values. We will 
also drop the "Time" columns as it is irrelevant.
• Now, we will split the credit card data with a split of 70-30 using train_test_split().
• train_test_split() function in scikit-learn is a useful utility for splitting a dataset into training and 
testing sets.
• Parameters
• X: Feature matrix
• Y: Target variable
• test_size: Proportion of the dataset to include in the test split. Here we have set the test_size as 0.3 
means 30% of the data we take as testing data set.
• random_state: we have set the seed for random number generation, to ensure the reproducibility

Applying Machine Learning Algorithm to Credit Card Dataset
• We will explore various machine learning algorithms to determine the most effective model for our 
binary classification problem.
• The task involves predicting one of the two class labels. We plan to access the performance of 
different algorithms, such as Random Forest and Decision Tree identify the most suitable solution for 
our specific problem
• Our approach involves constructing Random Forest and Decision Tree classifiers to identify the most 
effective model.

Decision Tree Algorithm 
The Decision Tree Algorithm is a supervised machine learning technique employed for both classification 
and regression tasks. Its objective is to create a training model capables of predicting the value of a target 
class variable.This is achieved by learning straighforward if-then-else decision rules derived from the 
patterns present in the training data.


Random Forest Algorithm
Random Forest is supervised Machine Learning algorithm. It creates a "forest" out of an ensemble of 
"decision trees", which are normally trained using the "bagging" technique. The bagging method's basic 
principal is that combining different learning models improved the outcome.To get a more precise and 
reliable forecast, random forest creates several decision trees and merges them.

We understand from the confusion matrix for the random forest as well as for decision tree

Class-Imbalance
• The Random Forest model works better than Decision Trees. In the presenece of a classImbalance issue, where genuine transactions account for over 99% of the dataset and credit 
card fraud transactions constitute only 0.17%.
• Training the model without addressing the imbalance can lead to biased predictions.
• Despite the apparent accuracy, such a model may not effectively capture the nuances of the 
minority class (fraud transactions) and may not generalize well to real-world situations.
• The class imbalance problem can be solved by various techniques. Oversampling is one of 
them

We will use the SMOT (Synthetic Minority Oversampling Technique, or SMOTE).It is the method 
of data augmentation for the minority class.

We can see that our model performed much better than the previous Random Forest classifier 
without oversampling.
We have applied the techniques to address the class imbalance issues and achieved an accuracy of 
more than 99%

We will import the pickle for dumping the dataframe and the model for future deployement.


