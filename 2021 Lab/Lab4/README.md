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
    <img src="img/header.jpeg" alt="Linear Regression" width="auto" height="auto">
  </a>

  

  <p align="center">
    Data Creation - Data anonymization - Timeseries<br \>
    <br />
    ·
    <a href="https://github.com/umaimehm/Intro_to_AI_2021/issues">Report Bug</a>
    ·
    <a href="https://github.com/umaimehm/Intro_to_AI_2021/issues">Request Feature</a>
  </p>



<!-- ABOUT THE LAB -->
## About The Lab





We will be using [pandas][pandas-doc], [sklearn][sklearn-doc]



## New imports

```python
from sklearn import preprocessing
# add as we go along
```

<details>
  <summary>Click to show all imports</summary>

```python
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline
from sklearn import preprocessing
```

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
From the matrix, we can see that Var1 and Result is highly correlated. We can also see that Var3 has a correlation.

![corrplot][corr]


</details>




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
[dfinfo]: img/dfinfo.png
[df2info]: img/df2info.png
[flightdata]: data/flight.csv

<!-- documentation -->
[pandas-doc]: https://pandas.pydata.org/docs/reference/index.html#api
[numpy-doc]: https://numpy.org/doc/stable/
[seaborn-doc]: https://seaborn.pydata.org/api.html
[sklearn-doc]: https://scikit-learn.org/stable/modules/classes.html


<!-- tutorials -->
[feature-eng-tutorial]: https://github.com/PacktPublishing/Python-Feature-Engineering-Cookbook
[pandas-cheatsheet]: https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf
[for-loop]: https://www.w3schools.com/python/python_for_loops.asp

<!-- links -->
[api-key]: https://frost.met.no/auth/requestCredentials.html
[regex]: https://www.geeksforgeeks.org/python-regex-cheat-sheet/
[solution]: solution.ipynb
[faker]: https://github.com/joke2k/faker
[laundromat]: https://github.com/navikt/laundromat
[frost]: https://frost.met.no/python_example.html



