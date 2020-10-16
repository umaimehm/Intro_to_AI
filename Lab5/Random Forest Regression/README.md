# Random Forest Regression

### What is Random Forest Regression?
A Random Forest is an ensemble technique capable of performing both regression and classification tasks with the use of multiple decision trees and a technique called Bootstrap and Aggregation, commonly known as bagging.The basic idea behind this is to combine multiple decision trees in determining the final output rather than relying on individual decision trees.<br>
Random Forest has multiple decision trees as base learning models. We randomly perform row sampling and feature sampling from the dataset forming sample datasets for every model. This part is called Bootstrap.<br>

![Decision Tree](https://media.geeksforgeeks.org/wp-content/uploads/20200516180708/Capture482.png)

### Implementation of Random Forest Regression on real life dataset:
1. Importing Python Libraries and Loading our Dataset into a Data Frame.
2. Splitting our dataset into training set and test set
3. Creating a Random Forest Regression model and fitting it to the training data
4. Visualizing the Random Forest Regression results



<br>The Jupyter notebook RandomForestRegression.ipynb consists of the steps to do Random Forest Regression with Boston.csv dataset.

Video Tutorial for Random Forest Regression with dataset boston.csv : https://web.microsoftstream.com/video/7cc7c496-79f6-4b92-b554-6b94b17f1e25?list=studio

### Task: Try performing Random Forest Regression on the position_salaries.csv dataset
