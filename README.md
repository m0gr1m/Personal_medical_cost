# Personal medical cost
><img src="https://github.com/m0gr1m/Personal_medical_cost/blob/main/cost.png?raw=true"  width="200" align="left"> Health problems and the high cost of medical services make it an extremely important part of our lives to have health insurance. Not only does it help to cover the cost of any treatment or surgery, but it also gives you the peace of mind that - in the case of an accident - you won't end up with a huge bill that you'll be paying for for the next decade.

------

# Data
[Insurance dataset](https://github.com/m0gr1m/Personal_medical_cost/blob/main/insurance.csv).

[Data review and hypothesis testing file](https://github.com/m0gr1m/Personal_medical_cost/blob/main/analysis_part_one.ipynb).

[Machine learning model file](https://github.com/m0gr1m/Personal_medical_cost/blob/main/model_ml.ipynb).

------

# Motivation

Working in a company that sells health insurance, it is very important to identify a group of customers and predict the possible cost they will generate in the future by using our services. This problem can be solved with a well-chosen regression model, while using statistical tests we can find out whether the customers differ significantly in terms of a given characteristic present in the data set. 

## Main goal
+ Build a regression model that determines individual medical costs billed by health insurance.

## Side goal
Using selected statistical tests, check whether:

+ women and men differ by bmi, smoking or charges,
+ smoking is associated with being overweight,
+ regions differ by the amount of insurance paid.

------

# Quick summary:

+ There are almost equal numbers of men and women in the dataset, as well as regions. There is a significant difference in the number of smokers; this is a much smaller group. 
+ The average customer is 39 years old, obese and has one child.
+ Our female and male customers do not differ in terms of bmi and charges, but it can be said that men are more likely to be smokers.

<center><img src="https://i.imgur.com/0AoI9PC.png" width="500"></center>

+ Smoking is not associated with bmi, and the cost of insurance paid out is not region-specific.
+ It should be noted that the biggest difference is in the amount of charges and the fact that the client smokes cigarettes; this is almost a fourfold increase in cost because of being smokers relative to a non-smoker. The following situation is illustrated by the graph below, which show that such a small group of people is responsible for a significant increase in overall mean charges.


<center><img src="https://i.imgur.com/UbQZV68.png" width="800"></center>

**Regression model:** 

We used the scikit-learn package and four algorithms when building the model:
+ Simple Linear Regression
+ Lasso Regression 
+ k-Nearest Neighbor Regression 
+ Bayesian Regression 

The metric we used to choose the best model was $R^2$, and the model that had the best value of it was **Lasso**.

The first model I built had a score of 75.57% and the plot of true values versus predictions showed a relatively poor model fit.  
Therefore, I decided to remove the outliers and run the procedure again. The final model seen below has an approximate 85% score of correct prediction values versus true values. 

<center><img src="https://i.imgur.com/GDNz7uS.png" width="800"></center>

As can be seen, the model does quite well in predicting charges up to a value of about $14,000. 
One might think that higher values are infrequent and probably linked to very rare, expensive-to-treat conditions or other factors that contribute to their high cost e.g. the requirement for regular medical care. 
Also, we previously found that cigarette smokers significantly overestimate the average charges, which may be related to for example: the frequency of lung cancer.
