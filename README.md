# Ex-04-Multivariate-Analysis:
## Aim:

To perform Multivariate EDA on the given data set.

##Explanation Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
Algorithm
## Step1:

Import the built libraries required to perform EDA and outlier removal.
## Step2:

Read the given csv file.
## Step3:

Convert the file into a dataframe and get information of the data.
## Step4:

Return the objects containing counts of unique values using (value_counts()).
## Step5:

Plot the counts in the form of Histogram or Bar Graph.
## Step6:

Use seaborn the bar graph comparison of data can be viewed.
## Step7:

Find the pairwise correlation of all columns in the dataframe.corr()
## Step8:

Save the final data set into the file.
## Code:
```
Developed by : Rakesh J.S
Registration Number : 212222230115

import pandas as pd
import numpy as py
import seaborn as sns
import matplotlib.pyplot as plt

df=pd.read_csv('SuperStore.csv')
df
df.head()
df.info()
df.describe()
df.isnull().sum()
df.dtypes

sns.scatterplot(df['Postal Code'],df['Sales'],hue=df['Row ID'])

sns.barplot(x=df['Row ID'],y=df['Sales'],data=df)

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

sns.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])

df.corr()
sns.heatmap(df.corr(),annot=True)
```
# Output:
## Data:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/5fb0bf08-8a69-40c9-9b02-b916f25550f2)

## Data head:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/0dc75325-b1bb-49fb-ac97-7c763766bc24)

## Data Information:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/ad8c7d1d-7f22-49a9-b59e-3eae0e654986)

## Data describe:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/24122424-f332-4d42-a1ae-269aabaadeb1)

## Data Null Values:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/731db795-9fee-4d19-b391-1641b0dc1d8c)

## Data Types:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/3cd88921-edf9-4e51-b65e-65d8f92e5c51)

## Scatterplot:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/6b6d4344-4ffc-4c8a-a2e8-a18e8d959b9d)

## Barplot:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/103c029e-7db0-4b8e-9b32-9e1d35daceca)
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/4fbf8689-6bc9-4fbf-89dc-48284b98eb62)
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/05cbc63b-bd17-4ca3-82b1-871233b12c1c)

## Correlation and Heatmap:
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/d2661b82-650b-4667-a5d2-9684856a8e46)
![image](https://github.com/rakesh9339/Ex-04-Multivariate-Analysis/assets/121115650/9aca5e7c-e72b-4b07-9877-481c07954c88)

# Result:

Thus the program to perform EDA on the given data set is successfully executed.
