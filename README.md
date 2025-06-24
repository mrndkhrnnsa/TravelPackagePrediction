# Travel Package Prediction ✈️🏖

(This project is submitted as the final requirement for the Data Science Bootcamp at Dibimbing.ID.)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               

## Project Background

Travel packages, which combine transportation, accommodation, and sometimes activities or tours, are increasingly popular among customers seeking convenience, cost savings, and curated experiences. Customers often purchase these packages to simplify travel planning, access exclusive deals, or ensure a seamless vacation experience. However, not everyone feels compelled to buy them. In the competitive travel and tourism industry, understanding the factors driving package purchases is crucial for businesses aiming to optimize their offerings and marketing strategies.

This project focuses on analyzing a travel package prediction dataset to uncover patterns in customer behavior and predict package purchases. By identifying the key drivers behind customer decisions, travel agencies can design targeted marketing campaigns, personalize recommendations, and enhance customer satisfaction. The insights gained will ultimately benefit businesses by increasing revenue, improving resource allocation, and fostering customer loyalty while enabling travelers to enjoy more tailored and value-driven experiences.

## Problem Statement

Travel agencies can often struggle to figure out which customers will buy their travel packages, which causes them to spend their resources marketing to everyone rather than focusing on just the right audience. This can lead to inefficient budget, missed revenue opportunities, and poor customer experiences. This project aims to identify factors influencing travel package purchases. The model precision, recall, F1-score, and ROC-AUC metrics impact on the marketing efficiency can then be used to measure the success of the project.

## Goals

- To determine customer profile and analyze their purchasing behaviour.
- To develop a prediction model that can predict the likelihood of customers purchasing a travel package.

## Objective

To develop a prediction model to predict the probability of travel package purchase based on each customer profile.

## Dataset

The dataset used for this project can be found on Kaggle: [Travel Package Dataset](https://www.kaggle.com/datasets/sanamps/tourpackageprediction)

## Data Dictionary

- **CustomerID:** Unique customer ID
- **Age:** Age of customer
- **TypeofContact:** How customer was contacted - Company Invited ot Self Inquiry
- **CityTier:** The development of a city (population, facilities, living standards, etc.) - Tier 1 > Tier 2 > Tier 3
- **DurationofPitch:** Duration of pitch by a salesperson to the customer
- **Occupation:** Occupation of customer
- **Gender:** Gender of customer
- **NumberofPersonVisiting:** Total number of persons planning to take the trip with the customer
- **NumberofFollowups:** Total number of follow-ups has been done by the salesperson after the sales pitch
- **ProductPitched:** Product pitched by the salesperson - Basic, Standard, Deluxe, Super Deluxe, King
- **PreferredPropertyStar:** Preferred hotel property rating by customer
- **MaritalStatus:** Marital status of customer
- **NumberofTrips:** Average number of trips taken in a year by customer
- **Passport:** Whether the has a passport or not  - 0: No, 1: Yes
- **PitchSatisfactionScore:** Sales pitch satisfaction score
- **OwnCar:** Whether the customers own a car or not - 0: No, 1: Yes
- **NumberofChildrenVisiting:** Total number of children with age less than 5 planning to take the trip with the customer
- **Designation:** Designation of the customer in the current organization
- **MonthlyIncome:** Gross monthly income of the customer

## Target

- **ProdTaken:** Whether the customer took the product or not

## Data Pre-Processing

1. Data Wrangling involved data cleaning such as fixing data quality (types, duplicates, and missing).
There were no duplicated data found and a few MAR data filled with Mice Imputation.
2. Feature Selection and Engineering involved:
- Encoding the categorical variables (`TypeofContact`, `Occupation`, `Gender`, `ProductPitched`, `MaritalStatus`, and `Designation`)
- Checking variables multicollinearity (`Designation` was dropped)
3. The data was then split into 80% train: 20% test ratio for modelling
4. Outliers were also removed from the train data set.
5. Standard Scaling was performed for Logistic Regression.

## Model Selection and Analysis

The base model Logistic Regression showed a training F1-score of 38.99% and testing F1-score of 43.60%. 

The strongest performing model with good generalization is the XGBoost with a training F1-score of 99.93% and testing F1-score of 79.19%. A tuned XGBoost model (without SMOTE) showed further improvement over all metrics with a testing F1-score of 81.21%.

## Features Importances

![Features Importances](features_importances.png)

1. **Product Pitched is Dominant:** The type of package offered significantly impacts customer purchasing decisions.
2. **City Tier**: The customer's demographic location affects their preferences.
3. **Number of Follow-ups:** Consistent engagement increases the likelihood of purchase.
4. **Other Demographic Factors:** Prefereed Propoerty Stars and Age Demographic also influences decision.

## Key Takeaways

1. **Lead with High-Converting Offers**  
   Start pitches with Basic or Standard packages to engage interest before upselling.

2. **Prioritize High-Potential Segments, While Supporting Others**  
   Focus on City Tier 3 and the 25–40 age group where conversion rates are highest, while continuing to personalize messaging for other segments.

3. **Strengthen Follow-Up & Personalization**  
   Set a minimum number of follow-ups per lead. Automate and personalize outreach, and tailor package suggestions based on customer preferences.

## Thank You 👍
