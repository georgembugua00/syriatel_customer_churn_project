# Customer Churn Predictor System for Syria Tel
![WhatsApp Image 2024-03-10 at 7 25 07 PM](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/268d0759-89f9-4e32-9035-55feb711a9c4)

# Overview
## Executive Summary:
This proposal outlines the implementation of a customer churn prediction system for Syria Tel's Sales and Marketing department. This system, leveraging the power of machine learning and data analytics, aims to address key challenges and unlock significant growth opportunities, ultimately enhancing profitability and customer satisfaction.

# Business Understanding
![WhatsApp Image 2024-03-10 at 7 25 05 PM](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/73c16c9e-30d8-4776-9511-3bee76f9a8d3)

## Problem Statement:
Syria Tel's Sales and Marketing department faces challenges such as:
1.	Low conversion rates: Attracting the wrong customer profile leads to wasted resources and high churn (customer defection).
2.	Ineffective campaigns: Lack of reliable data on consumer behavior hinders effective resource allocation, resulting in underwhelming campaign performance and a declining return on investment (ROI).
3.	Limited budget: A recent budget reduction necessitates more efficient and targeted marketing strategies.

## Objectives:
- Increased Profitability: Reduced churn and optimized campaigns will directly translate to higher customer lifetime value and improved profitability.
- Enhanced Efficiency: Data-driven insights guide resource allocation towards the most effective marketing strategies, maximizing ROI even within budget constraints.
- Competitive Advantage: By leveraging customer data effectively, Syria Tel can gain a competitive edge by offering targeted solutions and personalized experiences

## Proposed solution
Implementing a customer churn prediction system offers several advantages:

•	Proactive Customer Retention: Identify customers at high risk of churn, allowing the team to implement targeted retention strategies (e.g., loyalty programs, personalized offers) before they defect, saving valuable customers and reducing churn rates.

•	Data-Driven Decision Making: Gain deeper insights into customer behavior, preferences, and pain points. This empowers the Sales and Marketing department to:

•	Optimize Campaigns: Target high-potential customers with relevant and personalized offerings, leading to significantly improved conversion rates and ROI.

•	Focus on Customer Needs: Develop and deploy campaigns that address specific customer pain points, resulting in increased customer engagement, satisfaction, and loyalty.

# Data Understanding
-The data was sourced from Kaggle at https://www.kaggle.com/code/becksddf/churn-in-telecoms-dataset

Data Size: 
The dataset has 3,333 rows and 21 columns

Data Source:
The dataset contains information regarding Syriatel's customers behaviours such as total charge, total calls and total minutes. Also represented is the customer prefernces such as international plan ,voice mail plan. Finaly the customer demographics have been provided with columns such as state and area code.

## Data Types:
•	Object: 4 columns (state, phone number, international plan, voice mail plan)

•	Integer: 8 columns (account length, area code, number vmail messages, total day calls, total eve calls, total night calls, total intl calls, customer service calls)

•	Float: 8 columns (total day minutes, total day charge, total eve minutes, total eve charge, total night minutes, total night charge, total intl minutes, total intl charge)

•	Boolean: 1 column (churn)

## Data Pre-Processing
The following actions where take during the data pre-processing:
 
  - Converting the relevant interger columns into binary format using LabelEncoder
  
  -  Creating new features through feature engieering
  
  -  Outlining the ranking of features in descending order through feature selection.

## Data Analysis (EDA)

Exploratory data analysis was implemented inorder to transform the data into information that can used to source data insights. The following methods and technqiues were used to transform the data into information:

  1. Pivot Tables
  2. Feature Engineering
  3. Feature Selection
  4. Lambda functions

### Data Visualization
The seaborn and matplotlib libraries were utilized throughout the data visualization process.
 # 1. Univariate Analysis:
 This analysis investigates a variables relationship with itself for example its frequency or value counts.
### Pie Chart Representing Customer Churn
![pie_chart_churn](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/7dc76380-df36-4f4c-8818-f7c63fef5a45)

### Voice Mail Plan Count
![voicemail_plan_counts](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/ce6c3aff-ad0b-4d88-9f16-d5a36ab90ecf)

     
 # 2. Bivariate Analysis
 This analysis investigates the relationship between two variables for relationship between account length and customer churn. this bivariate analysis help paint a cause and effect image as to my customer churn was occuring.

### Bar Graph Represent State with Longest AccountS  
![longest_account_length_per_state](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/34e5d346-692f-4386-9441-3efe4bd0e631)

### Bar Graph Representing Relationship between Account Length in Periods and Churn

![account_length _churn](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/bd0a82d5-6891-4591-93fc-dabdad31cf13)
     
# 4. Multivariate Analysis

This investigate the relationship between two or more variables. This was accomplished using seaborns hue parameter and  matplotlibs subplots. This granted even more insights into customer churn key drivers

### Graph Representing the Relationship Between Maximum Account Lenght and Average Churn Rate
![maximum_account_length_by_churn](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/42fc28fd-d7d7-4b2e-b700-6952bc6abdfe)


![WhatsApp Image 2024-03-10 at 10 09 58 PM (1)](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/d73dc4fd-2f3d-49b9-ba22-4c5493a41bb9)

## Model Performance

1. Decision Trees Algorithm

The main classification metrics of interest were Precision, Recall and AUC-ROC score, this due the fact that the purpose of the model was to save the stakeholders money through correct classification of customers that are prone to churn. Below is a breakdown to the models performance 

•	**Precision:** Precision measures the proportion of true positive predictions among all positive predictions made by the model. In this case, the precision for predicting churn (True) is 0.91, indicating that out of all the customers predicted to churn, 91% actually did churn.

•	**Recall:** Recall measures the proportion of true positive predictions among all actual positive instances in the dataset. The recall for predicting churn (True) is 0.73, suggesting that the model correctly identified 73% of all churn cases.

•	**F1-score:** The F1-score is the harmonic mean of precision and recall, providing a balance between the two metrics. The F1-score for predicting churn (True) is 0.81, indicating a reasonable balance between precision and recall.

• **AUC-ROC score:** this score measures the model's ability to distinguish between positive and negative classes across different thresholds, is 0.861.

2. XGB Classifier Algorithm

The XGB Classifier Algorithm was deemed suitable for this due to it capabilities with handling imbalanced distributions. The classification metrics from the algorthim was above average with the following weakness:

- **Model Weaknesses:**

Balanced Precision and Recall for Non-Churn, Lower for Churn (True Class): While precision is high for both classes, recall for churners (0.80) is concerning. This means the model misses 20% of actual churners, potentially leading to lost revenue or missed retention efforts. More importantly the model showed signs of overfitting with it high accuracy and low recall for customer churn. 

## Various hyperparameters were introduced to mitigate this issue and produce a more profitable model. The following where the hyperparameters implemented:
    
1. learning_rate: Controls the step size for updating model weights during training

2. n_estimators: Specifies the number of decision trees (boosting rounds) in the ensemble model.

3. max_depth: Defines the maximum depth allowed for individual trees in the ensemble.

4. min_child_weight:  Sets the minimum sum of weights (hessian) required in a child node for further splitting.
5. gamma:Defines the minimum loss reduction required to create a new split in a leaf node.

6. reg_alpha: Controls the L1 regularization penalty on weight coefficients.

7. reg_lambda: Controls the L2 regularization penalty on weight coefficients (squared values).


## XGB Classifier Tuned Performance

After implementing the hyper parameters the models new performance was as follows:

Precision for the "True" class: 0.80
Recall for the "True" class: 0.80
F1-score for the "True" class: 0.80
Accuracy: 0.94

### Observation:

Precision: Precision measures the accuracy of positive predictions. In the first table, the precision for the "True" class is higher (0.91) compared to the second table (0.80). This indicates that in the first model, when it predicts a customer will churn (positive prediction), it is more likely to be correct.

Recall: Recall measures the ability of the model to correctly identify positive instances. In the first table, the recall for the "True" class is lower (0.73) compared to the second table (0.80). This suggests that the first model may miss more instances of actual churn (false negatives) compared to the second model.

F1-score: The F1-score is the harmonic mean of precision and recall, providing a balance between the two metrics. In the first table, the F1-score for the "True" class is slightly higher (0.81) compared to the second table (0.80), reflecting a slightly better balance between precision and recall.


## Limitations
![360_F_456528158_qxlh072scPnSUiOljmVQ0Ha09Nmt2klY](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/4563dde0-3a09-4e02-9bb4-ba4c2a1c7ae5)

The main limitations of the dataset was the limited data quantity. A small or biased dataset might not capture the full spectrum of customer behavior, leading to a model that performs well on the training data but generalizes poorly to unseen customers data or test data. 

**Feature relevance**: The features available in the dataset proved to be informative for ones for predicting churn however an inclusion of various variables may improve the system’s ability to provide more meaningful insights such as customer comments.

**Imbalanced distribution**: The dataset might have an imbalanced distribution of churners (101) and non-churners (566). This can bias the model towards the majority class and lead to poor performance in predicting the minority class (churners) however this was addreeses using SMOTE oversampling .

# Concluesion

## Recommendations

1.	**Focus on Customer Retention:** Given that "Total Charge" and "Customer Service Calls" are the top two features contributing to churn prediction, there should be a concerted effort to improve customer satisfaction and minimize the need for service calls. This may involve providing better service, resolving issues promptly, and offering incentives for long-term customers.

2.	**Monitor Usage Patterns:** Pay close attention to "Total Minutes," "Total International Calls," and "Total International Minutes" as they indicate usage patterns. Customers with high usage, especially in international calls, may be at a higher risk of churn. Understanding their needs and preferences can help tailor retention strategies.

3.	**Promote Additional Services:** The presence of "International Plan" as a significant feature suggests that customers with such plans may have different needs or behaviors. Targeted promotions or offers for international calling features could help retain these customers and attract new ones.

4.	**Improve Communication:** The "Number of Voicemail Messages" and "Voice Mail Plan" features indicate preferences for voicemail usage. Enhancing voicemail services or offering alternative communication channels based on customer preferences can improve satisfaction and retention.


5.	**Customer Engagement:** Since "Total Calls" and "Account Length" are also significant features, fostering ongoing engagement with customers and rewarding loyalty can help reduce churn. Special offers, loyalty programs, or personalized communications can enhance customer satisfaction and retention.

