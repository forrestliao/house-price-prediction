# house-price-prediction
Pratice house price prediction via classic ML methods.

Description
---
Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

### Practice Skills
- Creative feature engineering 
- Advanced regression techniques like random forest and gradient boosting

**Click Here to Visit My Notebook**: https://github.com/forrestliao/house-price-prediction/blob/main/regression.ipynb

Data Description
---

### File descriptions
- train.csv - the training set 1460
- test.csv - the test set 1459
- data_description.txt - full description of each column, originally prepared by Dean De Cock but lightly edited to match the column names used here
- sample_submission.csv - a benchmark submission from a linear regression on year and month of sale, lot square footage, and number of bedrooms

Description in chinese: https://blog.csdn.net/Nyte2018/article/details/89977261

![](https://i.imgur.com/EteAYi9.png)
There are 79 features in one record.

Feature Engineering
---

- Data understanding (I keep my insights of every data in a execl table: https://docs.google.com/spreadsheets/d/1kU7PWTi-uJc0_voyZRhOpwLX8EgI24WGgfX5EQ0CgHM/edit?usp=sharing)
- Analysis sale price(Target's information, such as count, mean, min, max, std, mid , etc.)
- Feature selection (find the features with highest pearson correlation coefficient)
- Missing Value imputation
- Outlier Detection
- check 4 assumptions (log transformation)


Linear regression
---

### using 2 variables 
- GrLivArea
- TotalBsmtSF

```
intercept: 5.4042589534395375
coefficient: [0.83500605 0.08188665]
Mean squared error: 0.06
Coefficient of determination: 0.60
```
Root Mean Squared Logarithmic Error(RMSLE): **0.26856 (56XX/6560)**


### use 5 variables

- OverallQual
- GrLivArea
- GarageCars
- TotalBsmtSF
- FullBath

```
intercept: 7.97560466907642
coefficient: [0.12794803 0.37965254 0.11780532 0.03863646 0.02639681]
Mean squared error: 0.03
Coefficient of determination: 0.81
```
![](https://i.imgur.com/n0j1Y1A.png)
RMSLE: **0.51109**

Random Forest
---
```
Mean squared error: 0.00
```
RMSLE: **0.35027**
![](https://i.imgur.com/tHEMweG.png)


XGboost
---
```
Mean squared error: 0.00
```

RMSLE: **0.35027 (5192/6560)**
![](https://i.imgur.com/8pC87Ye.png)


**Still keep going...**


Reference
---

- Data description in chinese: https://blog.csdn.net/Nyte2018/article/details/89977261
- 4 Assumptions of regression: https://researcher20.com/2009/11/12/%E8%BF%B4%E6%AD%B8%E5%88%86%E6%9E%90%E7%9A%84%E5%81%87%E8%A8%ADassumption-of-ols-regression/
- Heteroscedasticity:
    - https://en.wikipedia.org/wiki/Homoscedasticity
    - https://www.geeksforgeeks.org/heteroscedasticity-in-regression-analysis/
- XGBoost:
    - XGBoost usage: https://github.com/dmlc/xgboost/blob/master/demo/guide-python/sklearn_examples.py
    - XGBoost in practice: https://www.kaggle.com/mywishisworldpeace/kaggle-xgboost1
- Feature engineering: 
    - https://vinta.ws/code/feature-engineering.html
    - https://www.kaggle.com/pmarcelino/comprehensive-data-exploration-with-python?select=train.csv
    - https://yanwei-liu.medium.com/python%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E7%AD%86%E8%A8%98-%E5%8D%81%E4%B8%80-%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92%E7%9A%84%E8%B3%87%E6%96%99%E5%89%8D%E8%99%95%E7%90%86%E6%8A%80%E8%A1%93-4dbd27560743
    - 
