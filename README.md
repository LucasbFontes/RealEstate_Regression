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


# The Project

This project focus on trying to predict the Real Estate values from a certain city. I used 4 regression techniques: 

 - Linear Regression:
 - Ridge Regression:
 - Lasso Regression:
 - Random Forest Regression:

And other 3 metrics to validate the techniques:

 - MSE:
 - RMSE:
 - R2:
