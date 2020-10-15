
### Linear regression in ML?
Linear Regression is a supervised machine learning algorithm where the predicted output is continuous and has a constant slope. It’s used to predict values within a continuous range, (e.g. sales, price, income) rather than trying to classify them into categories (e.g. cat, dog). 


In other words linear regression uses traditional slope-intercept form or linear equation, where m and b are the variables our algorithm will try to “learn” to produce the most accurate predictions. x represents our input data and y represents our prediction.

y=mx+b (m is slop or coefficient or gradient and b is intercept)

### Steps:
We will follow these steps in this simple task

1) We will import the required the modules for this task. One of the important package is linear_model from sklearn. More details for this module can be read from   SKlearn documentation at https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html

2) After that we will load canada_per_capita_income from csv through panda module. 

3) In Step 3 we will Create linear regression object and pass 2 arguments as input and icome to its Fit() function. In other words we will use training data that has years and corresponding income and train a linear regression model using sklearn linear regression class.

4) In next step we will analyse Visual Represention of Linear Regression with matplotlib.

5) We will predict the per capita income using predict() function. 

6) Then we will see Proof of linear Equation and check its accuracy.

![linear_equation](https://user-images.githubusercontent.com/17771301/96145348-67766e80-0f05-11eb-8d54-807bdd5de6c7.png)
