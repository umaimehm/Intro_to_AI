<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]




<!-- PROJECT LOGO -->
<br />
<h3 align="center">Dave3625 - Lab4</h3>
<p align="center">
  <a href="https://github.com/umaimehm/Intro_to_AI_2021/tree/main/Lab4">
    <img src="img/header.jpg" alt="Linear Regression" width="auto" height="auto">
  </a>

  

  <p align="center">
    Training your first model<br \>
    <br />
    ·
    <a href="https://github.com/umaimehm/Intro_to_AI_2021/issues">Report Bug</a>
    ·
    <a href="https://github.com/umaimehm/Intro_to_AI_2021/issues">Request Feature</a>
  </p>



<!-- ABOUT THE LAB -->
## About The Lab

LAB TEXT



We will be using [pandas][pandas-doc], [sklearn][sklearn-doc]



## New imports

```python
from sklearn import metrics
from sklearn import preprocessing
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

```

<details>
  <summary>Click to show all imports</summary>

```python
%matplotlib inline

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

from sklearn import metrics
from sklearn import preprocessing
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

#Yes, I like to sort imports based on length

```

</details>


## Tasks
**1. Read in data.csv, and look for correlation between rows**


<details>
  <summary>How to read a csv from github</summary>

```python
url = "TEXT"
#Find the raw url from the github repo
df = pd.read_csv(url)
```

</details>

Use pandas .corr() to create a correlation matrix.
You can then plot the matrix to get a betre understanding for the data

<details>
  <summary>Hint</summary>

```python
#corrMatrix is the variable where you saved the correlation matrix

#Standard corr plot
plt.matshow(corrMatrix)
plt.show()

#Another style of corr plot
corrMatrix.style.background_gradient(cmap='coolwarm')
```
*Check out [this page][cmap] for other cmap (color maps) for the plot.*

From the matrix, we can see that Var1 and Result is highly correlated. We can also see that Var3 might have a correlation.

![corrplot][corr]


</details>

We can also look at the correlation with scatterplots:
This is the column with the highest correlation with Result plotted against it:

![scatter-plot][scatter1]

We can also plot more columns together, like this:

![scatter-combo][scatter2]

As we can see from this plot, different columns have different min/max values. To solve this we need to scale the columns to a given interval.
This can be done by importing sklearn  and use the preprocessing.MinMaxScaler().


<details>
  <summary>Scaling</summary>

To scale a dataset, you can run:

```python
x = df.values #returns a numpy array
scaler = preprocessing.MinMaxScaler().fit(x)
x = scaler.transform(x)
df = pd.DataFrame(x)
#To keep column names do
#df[list(df.columns)] = scaler.transform(df)
#instead of line 3 and 4
#But we want to just have a numeric id for now, since it will help us later.
```

Output
  
![scaling][scale1]

If you want to unscale, do:

```python
x = df.values #returns a numpy array
x = scaler.inverse_transform(x)
df = pd.DataFrame(x)
df.head()
```

![scaling][scale2]

Tip: If you put the scaled dataset in df2, you can compare them easy.

</details>

After scaling the data, we can plot them together in a new scatter plot

![scatter-scaled][scatter3]

Lets make an another scatterplot where we plot each column against "Result" (or column 6 after scaling)

```python
#Scatterplot all columns against last column
fig, ax = plt.subplots(df.shape[1]-1, figsize=(15, 15)) #Figsize ( lenght, height )
for i in range(df.shape[1]-1):   #This loop is why we wanted to keep column name numeric, and not keep original names
    
    ax[i].scatter(x = df[i], y = df[6])
    ax[i].set_xlabel("Column " + str(i))
    ax[i].set_ylabel("Y")
fig.tight_layout()
plt.show()

```


<details>
  <summary>Show output</summary>
  
![scatter-combo][scatterall]

If you compare this to the correlation plot, you'll identify the same columns having a relation

![corrplot][corr]
  
  </details>
  
## Let's train a model 

In the task above, we found that Var1 and Var3 had a high correlation with the output. Let'a try to train a model on Var1 and evaluate the result.

First let's split the set in a training and a testing set

```python
X = pd.DataFrame(df[0]) #Var1
y = pd.DataFrame(df[6]) #Result

#Now, split the set in training and testing set
#test_size = 0.33 tell the function that 1/3 of values should be put in test arrat
#Random state is a variable that seeds the random generator. In that way
#you'll get the same training and testing set each run
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.33, random_state=42)
```
More on [train-test split][traintest]

We now have 2/3 of the values in Var1 stored in X_train and 1/3 stored in X_test.
You can now create a linear regressor model:

```python
linear_regressor = LinearRegression()  # create object for the class
linear_regressor.fit(X_train, y_train)  # perform linear regression
Y_pred = linear_regressor.predict(X_train)  # make predictions
```
To see the result, you can plot the prediction against the result column

```python
plt.scatter(X_train, y_train)             #Plot blue dots with real data
plt.plot(X_train, Y_pred, color='red')    #Plot red line with prediction
plt.show()                                #Show the plot
print( "MSE = "+str(metrics.mean_squared_error(y_train,Y_pred))) #Calculate MSE
```
<details>
  <summary>Show output</summary>

![model 1][mod1]

</details>

Let's check how good our model works on the test data

```python
Y_pred = linear_regressor.predict(X_test)  # Predict the model on X_test
plt.scatter(X_test, y_test)
plt.plot(X_test, Y_pred, color='red')
plt.show()
print( "MSE = "+str(metrics.mean_squared_error(y_test,Y_pred)))
```
<details>
  <summary>Show output</summary>

![model 2][mod2]

</details>

By chance we got a lower error on the test set. This is good, because the lower MSE is, the more accurate is the model.

## More hints

This section will be updated after the first lab session

## Usefull links
You can find usefull information about feature engeneering [here][feature-eng-tutorial]

[pandas cheatsheet][pandas-cheatsheet]

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.






<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
<!-- shields -->
[issues-shield]: https://img.shields.io/github/issues/umaimehm/Intro_to_AI_2021.svg?style=for-the-badge
[issues-url]: https://github.com/umaimehm/Intro_to_AI_2021/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/umaimehm/Intro_to_AI_2021/blob/main/Lab1/LICENSE

<!-- images -->

[corr]: img/corr.png
[scatter1]: img/scatter1.png
[scatter2]: img/scatter2.png
[scatter3]: img/scatter3.png

[scatterall]: img/scatterall.PNG
[scale1]: img/scale1.png
[scale2]: img/scale2.png
[mod1]: img/mod1.png
[mod2]: img/mod2.png

<!-- documentation -->
[pandas-doc]: https://pandas.pydata.org/docs/reference/index.html#api
[numpy-doc]: https://numpy.org/doc/stable/
[seaborn-doc]: https://seaborn.pydata.org/api.html
[sklearn-doc]: https://scikit-learn.org/stable/modules/classes.html


<!-- tutorials -->
[feature-eng-tutorial]: https://github.com/PacktPublishing/Python-Feature-Engineering-Cookbook
[pandas-cheatsheet]: https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf
[for-loop]: https://www.w3schools.com/python/python_for_loops.asp
[traintest]: https://machinelearningmastery.com/train-test-split-for-evaluating-machine-learning-algorithms/

<!-- links -->
[api-key]: https://frost.met.no/auth/requestCredentials.html
[regex]: https://www.geeksforgeeks.org/python-regex-cheat-sheet/
[solution]: solution.ipynb
[faker]: https://github.com/joke2k/faker
[laundromat]: https://github.com/navikt/laundromat
[frost]: https://frost.met.no/python_example.html
[cmap]: https://matplotlib.org/stable/tutorials/colors/colormaps.html


