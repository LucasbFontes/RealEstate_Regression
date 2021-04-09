# Prediction of real state values using regression 

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

## Finding Correlations

One step in machine learning projects is to find the correlation between our resources and the label, mainly because it helps us to see that there is some relationship between them. If so, we can use it in our project, otherwise, it will be necessary to delete it. 

Since we have two kind of features: non-categorical and categorical, I'm going to divide in two different visualizations, for non-categorical data I'll use scatterplot and for categorical the boxplot.

To make it simple and short I'll show only one feature of each kind:

![correaltion](https://user-images.githubusercontent.com/68716835/113952772-bc2bdf80-97ec-11eb-9ce0-f84bb2ee88aa.PNG)

This chart show us 2 important informations: the correlation value and the p-value. The first show how our 2 axis are related, and in this case -0,70 indicates a highly negative correlation, which means that when I increase the transit_distance the price decreases(and it makes sense, right?). The p-value is the probability to observe a statiscal test at least as extrem as the observed value. Since our p-value is less than 0,01 we have strong evidence.

Now for the non-categorical data

![bh](https://user-images.githubusercontent.com/68716835/113953822-09a94c00-97ef-11eb-8de9-d36e407ab9ef.PNG)


It's clearly that there's no correlation between price_per_unit and transaction_date, the boxplots flutuates along the X-axis. Therefore this feature won't be considered when training the algorithm.

# Machine Learning Algorithms

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

This technique is based on improving the parameters of a given function, the best approach is to study the functions parameters and understand their impact. After that, it is recommended to create a dictionary containing the chosen parameters and the values you want to check. To proceed with the optimization it is commom to use a function called **GridSearchCV** that take all the parameters defined in the dictionary and test all kind of possible combinations among them, e.g., if I have created a dictionary containing 3 parameters and each of them has 3 differentes values, I'll have 3x3x3=27 different combinations, GridSearchCV will return the combinations that perform better given the metrics defined earlier(in this case: MSE, RMSE e R2).

As well as every technique GridSearchCV has it's disadvantages, for example the time spent to test all possibilites. In this project I used only 3 parameters because it was a 
personal project, to test my knowledge, but in a real project it will be as much parameters as necessary, which obviously will increase exponentially the time to choose the best parameters combination. 

To avoid this disadvantage is possible to use **RandomSearchCV**, which instead of test all of the possible combinations, selects randomly the parameters in the dictionary and test them. 

Below you can check the train model, before(left image) and after(right image), hyperparametrization:


![image](https://user-images.githubusercontent.com/68716835/114112643-26a75300-98b3-11eb-8e3c-7413f7703a62.png) ![image](https://user-images.githubusercontent.com/68716835/114112665-32931500-98b3-11eb-83c0-0b66d39a7414.png)
     

# Conclusion

This readme focused on showing some data analysis as well as machine learning techniques.The aim here is to present only a scracth from these techniques and concepts, to improve your learning I recommend check on youtube channels, medium posts and kaggle courses.

