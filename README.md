# Phase-2-project
Phase 2 project

## Business Understanding¶
Our stakeholder is a real estate company that is looking to expand its market to King County. They need to be provided with a reliable prediction model about how new home renovations might increase the estimated value of homes in the area, and by what amount. To do this we will use the data from King County to build a model that will provide us with features that are important in determining the housing prices in the area.

## Data Understanding
Once we have loaded the data from King County we can use it to build our model. The data contains information on the price of the property, the square feet of the living area and the year the property was renovated to name a few. After loading our data we can see that most of our data is numerical and has has some columns that are missing like waterfront and yr_renovated, in order to solve this we will clean this data. Their is also some data which is not relevant to our model which we will remove.

From our observation we can see that:
The house data is from the year 1900-2015
The condition of the house is from 1-5
The grading system starts from 3-15
The is a '?' on sqft_basement which indicates that it is an object insead of it being numeric.
We have an outiler which is 33 bedrooms when we have a mean of 3.

## Continuous data analysis
We will use a histogram to show our data being positively skewed. In order to do this we will run a log transformation to make them be more normal

## Making our data categorical
We will drop the house with 33 bedrooms because it is the only outlier we will do this when cleaning the data.

From my analysis knowing when the property has been renovated or not is much better than the year the property was renovated.

We can also see that their was not much activity going on interms of renovations until the year 1982.

## Data Preparation
We will start by removing the rows with the null values in yr_renovated because we do not know whether they have been renovated or not. We will also remove the basement values which are not numbers. This will allow us to have plenty of data to use after removing them. Finally we will remove the outliers in the bedroom as well.

## Checking for Multicollinearity
When we have variables that have a high correlation to one another then we will have a challange with our regression analysis, which will make our results not understandable. In order to fix this problem we will search for variables that are high in correlation and remove them. We will remove the bathrooms and sqft_basement.

## Normalizing
The data we have is positively skewed which means we will have to perform a log transformation to ensure it has a more normal distribution. After doing this we will standardise our data by making the mean to be 0.

## One Hot Encode
In order to transform our categorical data we will use one hot encoding. This is so as to not have too many predictors for the year built we will categorize them into 5 year increments.

## Model 1
With our first model we used all the available predictors which got us an R^2 value of 0.622 which is resonable, which allows us to explain 62% of variations of our model. conditions and std_above had p-values which were greater than 0.05 which we will remove in our next model.

## Model 2
We will remove the two predictors which have lowered our R^2 score. Our Skew and Kurisis is still high. We will run a log transformation on the prices as well.

## Model 3
After the log transformation on the prices we can see an improvement on the distribution which is more normal. The improved Skewness is now from highly positive to slightly negative. The Improved skew is now between -0.5 and 0.5 which now means that the data is now very symmetrical. Our R^2 value has also increased to about 63.8% of the variance which is explained by the model.
![download](https://user-images.githubusercontent.com/91674285/176925837-5b36899f-e9ac-43e7-b1ae-9c89ad88b1ff.png)

## Homescedasticity
We will run a scatter plot to show homescedasticity, this will help us know that the error is constant along the values of our dependent variable. This will also provide us with a solid explainable place to start working on our analysis and forecasting of housing prices at King County over the next years
## Training
With training and testing being similar, we can expect our model to perform similarly on different data.
the accuracy of the model is at 61.2%
![image](https://user-images.githubusercontent.com/91674285/176941215-f06fd836-4d5f-461c-bead-0852c5429417.png)

## Conclusion
With our final model our regression results indicate that the R^2 value is at 0.616 meaning it is 61.16% of the variance that is explained by our model. Our results also tells us that the skewness is at -0.007 which is between - 0.5 to 0.5 this means that the data is symmetrical and it satisfies the normality assumption. Their is also an assumption that for linear regression that the data must be homoscedastic meaning that the different samples we have should have the same variance. To check this we plotted a scatterplot and viewed that the data indeed was homoscedastic and did not have any cone like shape which would indicate that our data was heteroscedastic. We also observed that the living space had the strongest relationship with how the house priced at. Its t-value came in at 47.2 which indicates how statistically significant the coefficient is. It also makes sense that the living space will have the strongest determining factor to the price of a property because of the time spent inside the house and having a large living area generally means that more rooms making it more appealing to potential buyers. The renovated homes have a t-value of 6.8 which is not as high. this data tells us that for non-renovated homes are heavily outweighed than the ones of renovated homes. This will give our stakeholder a grasp of the type of houses available at King County and the specification of what makes the value of a house appeciate in value or sell for.

