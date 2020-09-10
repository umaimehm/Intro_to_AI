## Featured-Engineering
Example 01

### Exercise 1: Outlier Detection and Removal Using Percentile technique



##### 1: First we need to import two libraries panda and matplotlib on your jupyter notebook


import pandas as panda
from matplotlib import pyplot as plt


##### 2: We need to read data.we create a variable and assign data_set file. 

dataframe = panda.read_csv("data_set.csv")


##### 3: head() function is used to visulize and test the data types inside the object. In short it will help you to know either your data set is valid or not.

dataframe.head()


##### 4: "shape" attribute is used to return dimentionality of dataframe in form of tuple, In simple it shows all the rows and columns of the dataset.

dataframe.shape


##### 5: We already imported the "matplotlib" library in start, we can use this library to form a visual distribution of data. (for example, histogram etc

plt.hist(dataframe.age, bins=10, rwidth=0.8)
plt.xlabel('Age')
plt.ylabel('Count')
plt.show()


##### 6: Here comes the tricky part, we need to detect outliers, there are many ways to do that, domain knowlegde is import to detect outliers but if the data is big and complex then mostly we use different techniques such as percentile. in the example we have created a veriable "thresold_max" where we will try to detect outlier in age field using percentile technique (quantile()).

thresold_max = dataframe['age'].quantile(0.90)


##### 7: Now, we will be abile to extract the max limit or upper bound of data points.

thresold_max


##### 8: Here, will be abile to extract the lower limit.

thresold_min = dataframe['age'].quantile(0.10)
thresold_min


##### 9: To have visulaized outcome of the data which is below to the minimum limit.

dataframe[dataframe['age']<thresold_min]


##### 10: Now, lets remove the the outliers and clean the data, as now we have max limit [thresold_max] and min limit[thresold_min].

new_dataframe=dataframe[(dataframe['age']<thresold_max) & (dataframe['age']>thresold_min)]



##### 11: Now we will be able to recognize that all the outlier have been detected and removed.

new_dataframe.shape
new_dataframe

