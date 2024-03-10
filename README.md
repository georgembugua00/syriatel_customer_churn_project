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

## DATA UNDERSTANDING
-The data was sourced from Kaggle

Data Size: 
The dataset has 3333 rows and 21 columns

Data Source:
The dataset contains information regarding Syriatel's customers behaviours such as total charge, total calls and total minutes. Also represented is the customer prefernces such as international plan ,voice mail plan. Finaly the customer demographics have been provided with columns such as state and area code.

Data Types:
•	Object: 4 columns (state, phone number, international plan, voice mail plan)
•	Integer: 8 columns (account length, area code, number vmail messages, total day calls, total eve calls, total night calls, total intl calls, customer service calls)
•	Float: 8 columns (total day minutes, total day charge, total eve minutes, total eve charge, total night minutes, total night charge, total intl minutes, total intl charge)
•	Boolean: 1 column (churn)

Data Pre-Processing
The dataset was cleaned and pre-processed into to make it suitable for modelling and presentation. The following actions were taken while data cleaning:
  
  - Dropping Whitestrips
  
  - Dropping insignificant columns

The following actions where take during the data pre-processing:
 
  - Converting the relevant interger columns into binary format using LabelEncoder
  
  -  Creating new features through feature engieering
  
  -  Outlining the ranking of features in descending order through feature selection.

# EDA
![international_churn](https://github.com/georgembugua00/syriatel_customer_churn_project/assets/151632200/841edd84-23b1-405e-b0f9-85f6783401bd)


## MODELING

Logistic Model Performance: the Logistic Regression's overall performance was classified as follows starting with the main objective of the model: 	

Precision - Precision for class 0 (customers who do not churn) is high with it being correct 85% of the time. However the precision for class 1 (customers who churn) is relatively low (0.43), indicating it is correct only 43% of the time. Since precision of the system is important introduction of Hyperparmeter will be nesscary before it can be implememented

•	Recall:
Recall for class 0 (customers who do not churn) is high (0.99), indicating that the model correctly identifies the vast majority of customers who do not churn and for class 1 (customers who churn) is very low (0.03), indicating that the model misses the majority of customers who actually churn.

•	F1-score:
The F1-score, which balances precision and recall, is higher for class 0 (0.92) compared to class 1 (0.06). This reflects the imbalance in the precision and recall values.

### Random Forest Performance**

**• Precision:**

Class 0 (not churned): 97% of the customers predicted as not churned by the model are actually not churned. This indicates the model is good at identifying true negatives (correctly classifying customers who won't churn).
Class 1 (churned): 98% of the customers predicted as churned by the model actually churned. This suggests the model is also good at identifying true positives (correctly classifying customers who will churn).

**• Recall:**

Class 0 (not churned): The model correctly identifies 100% of the actual non-churning customers. This is an ideal scenario, meaning the model doesn't miss any true negatives.
Class 1 (churned): The model identifies 85% of the actual churners. While this is still good, it indicates that the model misses 15% of the actual churners, which could be potential customers to focus retention efforts on.

**• F1-score:**

Class 0 (not churned): 0.99, indicating a good balance between precision and recall for the non-churning class.
Class 1 (churned): 0.91, suggesting a slightly lower balance between precision and recall for the churned class, due to the lower recall.

Feature Importance

1.	Total Charge (0.288462): The total amount charged to the customer, which indicates the revenue generated from each customer.
2.	Customer Service Calls (0.140143): The number of customer service calls made by the customer, which may indicate dissatisfaction or issues with the service.
3.	Total Minutes (0.119068): The total number of minutes used by the customer, which may correlate with their usage patterns and engagement with the service.
4.	International Plan (0.097676): Whether the customer has an international calling plan, which may indicate their usage behavior and willingness to pay for additional services.
5.	Total International Calls (0.054485): The total number of international calls made by the customer, which may indicate their communication needs and preferences.
6.	Total International Minutes (0.051449): The total number of international minutes used by the customer, which may also indicate their communication needs and preferences.
7.	Total International Charge (0.050201): The total charges incurred from international calls, which may reflect the customer's usage and spending behavior.
8.	Total Calls (0.043529): The total number of calls made by the customer, which may indicate their level of engagement with the service.
9.	Account Length (0.040044): The length of time the customer has been with the service, which may indicate their loyalty and satisfaction.
10.	Number of Voicemail Messages (0.038595): The number of voicemail messages received by the customer, which may indicate their communication preferences and engagement with the service.
11.	State (0.032340): The state in which the customer resides, which may reflect regional differences in usage patterns and demographics.
12.	Voice Mail Plan (0.031999): Whether the customer has a voicemail plan, which may indicate their communication preferences and usage behavior.
13.	Area Code (0.012010): The area code associated with the customer's phone number, which may also reflect regional differences in usage patterns and demographics.

Recommendations

1.	Focus on Customer Retention: Given that "Total Charge" and "Customer Service Calls" are the top two features contributing to churn prediction, there should be a concerted effort to improve customer satisfaction and minimize the need for service calls. This may involve providing better service, resolving issues promptly, and offering incentives for long-term customers.

2.	Monitor Usage Patterns: Pay close attention to "Total Minutes," "Total International Calls," and "Total International Minutes" as they indicate usage patterns. Customers with high usage, especially in international calls, may be at a higher risk of churn. Understanding their needs and preferences can help tailor retention strategies.

3.	Promote Additional Services: The presence of "International Plan" as a significant feature suggests that customers with such plans may have different needs or behaviors. Targeted promotions or offers for international calling features could help retain these customers and attract new ones.

4.	Improve Communication: The "Number of Voicemail Messages" and "Voice Mail Plan" features indicate preferences for voicemail usage. Enhancing voicemail services or offering alternative communication channels based on customer preferences can improve satisfaction and retention.


5.	Customer Engagement: Since "Total Calls" and "Account Length" are also significant features, fostering ongoing engagement with customers and rewarding loyalty can help reduce churn. Special offers, loyalty programs, or personalized communications can enhance customer satisfaction and retention.

