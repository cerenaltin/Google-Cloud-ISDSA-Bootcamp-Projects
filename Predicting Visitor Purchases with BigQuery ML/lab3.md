# Predicting Visitor Purchases with BigQuery ML

## Overview
BigQuery ML (BigQuery machine learning) is a feature in BigQuery where data analysts can create, train, evaluate, and predict with machine learning models with minimal coding.
The Google Analytics Sample Ecommerce dataset that has millions of Google Analytics records for the Google Merchandise Store loaded into BigQuery. In this lab, We used this data to run some typical queries that businesses would want to know about their customers' purchasing habits.

### Objectives

-	Use BigQuery to find public datasets
-	Query and explore the ecommerce dataset
-	Create a training and evaluation dataset to be used for batch prediction
-	Create a classification (logistic regression) model in BigQuery ML
-	Evaluate the performance of your machine learning model
-	Predict and rank the probability that a visitor will make a purchase

#### Scenario
Your data analyst team exported the Google Analytics logs for an ecommerce website into BigQuery and created a new table of all the raw ecommerce visitor session data for you to explore. Using this data, you'll try to answer a few questions.

- Question: Out of the total visitors who visited our website, what % made a purchase?

- Question: What are the top 5 selling products?

- Question: How many visitors bought on subsequent visits to the website?

Analyzing the results, we can see that (11873 / 729848) = 1.6% of total visitors will return and purchase from the website. This includes the subset of visitors who bought on their very first session and then came back and bought again.

Your team decides to test whether these two fields are good inputs for your classification model:
-	totals.bounces (whether the visitor left the website immediately)
-	totals.timeOnSite (how long the visitor was on our website)
Question: Looking at the initial data results, do you think time_on_site and bounces will be a good indicator of whether the user will return and purchase or not?
Answer: It's often too early to tell before training and evaluating the model, but at first glance out of the top 10 time_on_site, only 1 customer returned to buy, which isn't very promising. Let's see how well the model does.

After evaluating our model we get a roc_auc of 0.72, which shows that the model has not great predictive power. Since the goal is to get the area under the curve as close to 1.0 as possible, there is room for improvement.

