# Prediction of real state values using regression [Under Construction]

This analysis is part of Microsoft Course for Data Scientist. In this notebook the aim is to find the a good real estate predicting model. Throughout this Readme I'll explain the approach choosed as well as the metrics and others Machine Learning techniques. If you want to check the code, you can click [here](https://github.com/LucasbFontes/RealEstate_Regression/blob/main/02%20-%20Real%20Estate%20Regression%20Challenge%20(1)%20(1).ipynb) 

**Citation**: The data used in this exercise originates from the following study:

> *Yeh, I. C., & Hsu, T. K. (2018). Building real estate valuation models with comparative approach through case-based reasoning. Applied Soft Computing, 65, 260-271.*
>
> It was obtained from the UCI dataset repository (Dua, D. and Graff, C. (2019). [UCI Machine Learning Repository]([http://archive.ics.uci.edu/ml). Irvine, CA: University of California, School of Information and Computer Science).

# The dataset

This dataset has 414 rows and 7 columns:

- **transaction_date** - the transaction date (for example, 2013.250=2013 March, 2013.500=2013 June, etc.)
- **house_age** - the house age (in years)
- **transit_distance** - the distance to the nearest light rail station (in meters)
- **local_convenience_stores** - the number of convenience stores within walking distance
- **latitude** - the geographic coordinate, latitude
- **longitude** - the geographic coordinate, longitude
- **price_per_unit** house price of unit area (3.3 square meters)

In this case our variable to be predicted will be price_per_unit.


# The Project

This project focus on trying to predict the Real Estate values from a certain city. I used 4 regression techniques: 

 - Linear Regression: It's an equation that estimates a variable (in this case price_per_unit) based on others variables. This equation is found when we plot the data into a scatterplot and try to plot the best list throught the data. The plot has to be a straight line, otherwise it won't be linear.
 - SVR: The **S**upport **V**ector **R**egression uses the principle of Support Vector Machine to predict value through regression. It's main difference when compared to "simple regressions" is that although a simple regression focus on minimize the MSE(I'll take about it below) the SVM focus on fit the error within a threshold.   
 - Random Forest Regression: It works as multiples Decisions Trees, in each decision tree the algorithm selects, randomly, some features of our dataset and then separate the data following the decision tree logic. By the end of this logic, one DT provides one value as answer. After all decision trees had provide an answer of it's own, the final answer comes as a mean value of all others answers. 


And other 3 metrics to validate the techniques:

 - MSE: **M**ean **S**quared **E**rror measures of the squares of the erros, which means that we take the average squared difference between the estimated value and the actual value. 
 - RMSE: The **R**oot **M**ean **S**quared **E**rror corresponds to the square root of the MSE, a value of 0 indicates a perfect fit. 
 - R2: Indicates how close the data are from the adjusted regression line.

After trained the data with the 3 algorithms listed above, I chose to proceed with Random Forest, when compared with the others RF gave me the best MSE and, therefore, better RMSE, the R2 had a good result as well. 

# Hyperparameter Optimization

This technique is based on improve the parameters of a given function, the best approach is to study the parameters of a given function and understand it's impact.  

 
