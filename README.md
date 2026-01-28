# MLOPS-Test

Author - Jayesh R 

This repo includes my MLOPS knowledge with notes and Projects.


Why MLOps?

So a DevOps engineer deploys software and maintains the CI/CD piplelines, Easy. But it's complex with ML is involved - Data vailditaion( keeps track of what datasets are given to the ML) and Data versioning ( what kind of datasets are given ) and mointroing- Model Drift , Accuracy and Prcision.

Basic workflow - 

DG → EDA → Pre-Processing → Feature Engineering → Feature Selection → Model Training → Evaluation.

Example to understand - 
House pricing :

1. DG - Raw Data like where the house is located and how much does it cost and etc.
2. EDA - We see the use ful stuff like price and size of the house and location.
3. Pre processing - We convert to Computer form
    City → 1
    Town → 0
4. Feature Eng - We build feature - House cost = size x sqft price , small or big house
5. Feature selection - we keep it clean and filter the features - cost,sqft,price imp and rooms is less impactful as sqft says it all.
6. Model Trains - Data is split and the model learns as the size and location is better the price goes up (Linear Regression) .
7. Metrics (Regression):

MAE = 3L

RMSE = 4L

R² = 0.91


Git is a VSC/SCM

- Git and Github is very important for MLops and we need to version all the data set to ML to train.
- Collobration is needed and git/github is useful

  


