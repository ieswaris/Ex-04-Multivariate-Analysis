# Ex-04-Multivariate-Analysis

# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1
Import the built libraries required to perform EDA and outlier removal.

# STEP 2
Read the given csv file

# STEP 3
Convert the file into a dataframe and get information of the data.

# STEP 4
Return the objects containing counts of unique values using (value_counts()).

# STEP 5
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8
Save the final data set into the file

PROGRAM
```
Name : Eswari S
Register Number : 212221220012

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT
# DATA

![image](https://user-images.githubusercontent.com/127847210/230835397-aed2a8e1-caa0-4a3b-8da0-c02cf7ce0deb.png)

# Data.info

![image](https://user-images.githubusercontent.com/127847210/230835438-d7ad29a1-f1eb-4eec-8660-0df785100cad.png)

# Data.describe

![image](https://user-images.githubusercontent.com/127847210/230835477-bfa6c5ea-4c07-416c-94e4-ddf5c2f2bc75.png)

# Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/127847210/230835514-42eead54-3920-4aff-aea5-9bbf596cad4c.png)

![image](https://user-images.githubusercontent.com/127847210/230835661-fe6fbc21-77fc-4c22-8b5b-d5c1b82a3521.png)

# DATA TYPES

![image](https://user-images.githubusercontent.com/127847210/230835688-49dccf15-797f-47c2-ad97-f125804ab1ee.png)

# SCATTER PLOT

![image](https://user-images.githubusercontent.com/127847210/230835713-0ecb9807-2d84-4b24-8c2e-068fb4e80f10.png)

# BAR PLOT
![image](https://user-images.githubusercontent.com/127847210/230835760-4b6eed39-f52c-4f3e-aec9-747315ca5dc9.png)

![image](https://user-images.githubusercontent.com/127847210/230835779-53582dfe-eb4c-4115-a4c3-d78f3a381ed7.png)

![image](https://user-images.githubusercontent.com/127847210/230835808-b4d33f66-1895-4f00-a537-7e10bf889422.png)

![image](https://user-images.githubusercontent.com/127847210/230835846-bb39fdf5-7e72-470c-a2ad-35f6f778a484.png)

# CORRELATION COEFFICIENT INTERPRETATION

![image](https://user-images.githubusercontent.com/127847210/230835882-5c725adc-6acb-42a7-a9c1-7f3359d64df1.png)

# HEATMAP

![image](https://user-images.githubusercontent.com/127847210/230835897-f118f307-3677-46a4-b13d-62ccb74ef6c1.png)

# RESULT

Thus we have read the given data and performed the multivariate analysis with different types of plots.

