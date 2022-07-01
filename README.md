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
