# Assignment-based Subjective Questions
1. From your analysis of the categorical variables from the dataset, what could you infer about their effect on the dependent variable?
Ans: From the above observations from boxplot and heat maps
•	The year box plots indicates that more bikes are rent during 2019.
•	The season box plots indicates that more bikes are rent during fall season.
•	The working day and holiday box plots indicate that more bikes are rent during normal working days than on weekends or holidays.
•	The month box plots indicates that more bikes are rent during september month.
•	The weathersit box plots indicates that more bikes are rent during Clear, Few clouds, Partly cloudy weather.

2. Why is it important to use drop_first=True during dummy variable creation?
Ans: It is important to use drop_first function, as it helps in reducing the extra column created during dummy variable creation.

3. Looking at the pair-plot among the numerical variables, which one has the highest correlation with the target variable?
Ans: Highest correlation noted with ‘registerd’ variable as per initial analysis but registered is nothing but another form for target variable so not considering that and from plot it is evident that "temp" variable has the highest correlation with target variable


4. How did you validate the assumptions of Linear Regression after building the model on the training set?
Ans: Mostly his can be validated by plotting a scatter plot between the features and the target otherwise it can be also validate based on below 5 assumptions
•	(Independence of residuals) No auto-correlation 
•	Linearity should be visible among variables (Linear relationship validation)
•	There shouldn’t be any visible pattern in residual values (Homoscedasticity)
•	Error terms should be normally distributed (Normality of error terms)
•	Multicollinearity should be insignificant among variables (Multicollinearity check)

 


5. Based on the final model, which are the top 3 features contributing significantly towards explaining the demand of the shared bikes?
Ans: From the model these three Yr_1(2019),Temp(temperature), season_winter(winter season) took the major share to represent positive significance for demand


General Subjective Questions

1. Explain the linear regression algorithm in detail.
Ans: Linear Regression is a machine learning algorithm which is based on supervised learning category. It finds a best linear-fit relationship on any given data, between independent (Target) and dependent (Predictor) variables. In other words, it creates the best straight-line fitting to the provided data to find the best linear relationship between the independent and dependent variables. Mostly it uses Sum of Squared Residuals Method.
Linear regression is of the 2 types:
i. Simple Linear Regression: It explains the relationship between a dependent variable and only one independent variable using a straight line. The straight line is plotted on the scatter plot of these two points.
Formula for the Simple Linear Regression:
Y=β0+β1X1 +ϵ
ii. Multiple Linear Regression: It shows the relationship between one dependent variable and several independent variables. The objective of multiple regression is to find a linear equation that can best determine the value of dependent variable Y for different values independent variables in X. It fits a ‘hyperplane’ instead of a straight line.
Formula for the Multiple Linear Regression:
Y=β0+β1X1+β2X2+…+βpXp+ϵ
The equation of the best fit regression line Y = β₀ + β₁X can be found by the following two methods:
· Differentiation
· Gradient descent
We can use statsmodels or SKLearn libraries in python for the linear regression.


2. Explain the Anscombe’s quartet in detail.
Ans: Anscombe’s Quartet was developed by statistician Francis Anscombe. It comprises four datasets, each containing eleven (x, y) pairs. The essential thing to note about these datasets is that they share the same descriptive statistics. But things change completely, and I must emphasize COMPLETELY, when they are graphed. Each graph tells a different story irrespective of their similar summary statistics. 
  

The summary statistics show that the means and the variances were identical for x and y across the groups: 
•	Mean of x is 9 and mean of y is 7.50 for each dataset. 
•	Similarly, the variance of x is 11 and variance of y is 4.13 for each dataset 
•	The correlation coefficient (how strong a relationship is between two variables) between x and y is 0.816 for each dataset 
When we plot these four datasets on an x/y coordinate plane, we can observe that they show the same regression lines as well but each dataset is telling a different story:


  

•	Dataset I appears to have clean and well-fitting linear models. 
•	Dataset II is not distributed normally. 
•	In Dataset III the distribution is linear, but the calculated regression is thrown off by an outlier. 
•	Dataset IV shows that one outlier is enough to produce a high correlation coefficient. 
 

This quartet emphasizes the importance of visualization in Data Analysis. Looking at the data reveals a lot of the structure and a clear picture of the dataset. 

3. What is Pearson’s R?
Ans: Pearson’s R was developed by Karl Pearson and it is a correlation coefficient which is a measure of the strength of a linear association between two variables and it is denoted by ‘r’. it has a value between +1 and −1, where 1 is total positive linear correlation, 0 is no linear correlation, and −1 is total negative linear correlation.
Mathematically, Pearson’s correlation coefficient is denoted as the covariance of the two variables divided by the product of their standard deviation. The form of the definition involves a “product moment”, that is, the mean (the first moment about the origin) of the product of the mean-adjusted random variables; hence the modifier product-moment in the name.

 



4. What is scaling? Why is scaling performed? What is the difference between normalized scaling and standardized scaling? 
Ans: Scaling is the process to normalize the data within a particular range. Many times, in our dataset we see that multiple variables are in different ranges. So, scaling is required to bring them all in a single range.
The two most discussed scaling methods are Normalization and Standardization. Normalization typically scales the values into a range of [0,1]. Standardization typically scales data to have a mean of 0 and a standard deviation of 1 (unit variance).
 
Formula of Normalized scaling: 
X = x-min(x)/max(x)-min(x)
Formula of Standardized scaling:
X = x-mean(x)/sd(x)


5. You might have observed that sometimes the value of VIF is infinite. Why does this happen?
Ans: If there is perfect correlation, then VIF = infinity. A large value of VIF indicates that there is a correlation between the variables. If the VIF is 4, this means that the variance of the model coefficient is inflated by a factor of 4 due to the presence of multicollinearity. 
 
When the value of VIF is infinite it shows a perfect correlation between two independent variables. In the case of perfect correlation, we get R-squared (R2) =1, which lead to 1/ (1-R2) infinity. To solve this we need to drop one of the variables from the dataset which is causing this perfect multicollinearity. 

6. What is a Q-Q plot? Explain the use and importance of a Q-Q plot in linear regression.

Ans:  The quantile-quantile (q-q) plot is a graphical technique for determining if two data sets come from populations with a common distribution. 
 
Use of Q-Q plot: 
A q-q plot is a plot of the quantiles of the first data set against the quantiles of the second dataset. By a quantile, we mean the fraction (or percent) of points below the given value. That is, the 0.3 (or 30%) quantile is the point at which 30% percent of the data fall below and 70% fall above that value. A 45-degree reference line is also plotted. If the two sets come from a population with the same distribution, the points should fall approximately along this reference line. The greater the departure from this reference line, the greater the evidence for the conclusion that the two data sets have come from populations with different distributions. 
 
Importance of Q-Q plot: 
When there are two data samples, it is often desirable to know if the assumption of a common distribution is justified. If so, then location and scale estimators can pool both data sets to obtain estimates of the common location and scale. If two samples do differ, it is also useful to gain some understanding of the differences. The q-q plot can provide more insight into the nature of the difference than analytical methods such as the chi-square and Kolmogorov-Smirnov 2-sample tests. 
 
