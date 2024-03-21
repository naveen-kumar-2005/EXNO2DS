# Name:R.Naveen kumar
# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
 ```
 import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![alt text](image.png)
```
df.head(10)
```

![alt text](image-1.png)
```
df.tail(10)
```
![alt text](image-2.png)
```
df.info()
```
![alt text](image-3.png)
```
df.describe()
```
![alt text](image-4.png)
```
df.shape
```
![alt text](image-19.png)
```
df.set_index("PassengerId",inplace=True)
df["Survived"].value_counts()
```
![alt text](image-5.png)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![alt text](image-6.png)
```
sns.countplot(data=df,x="Survived")
```
![alt text](image-7.png)
```
df.Pclass.unique()
```
![alt text](image-20.png)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![alt text](image-8.png)
```
sns.countplot(data=df,x="Survived")
```
![alt text](image-9.png)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5)
```
![alt text](image-10.png)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![alt text](image-11.png)
```
df.boxplot(column="Age",by="Survived")
```
![alt text](image-12.png)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![alt text](image-13.png)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![alt text](image-14.png)
```
fig,ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass",y="Age",hue="Gender",data=df)
```
![alt text](image-15.png)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![alt text](image-16.png)
```
## Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![alt text](image-17.png)
```
sns.pairplot(df)
```
![alt text](image-18.png)
```



# RESULT
        Thus, the Exploratory Data Analysis on the given data set was performed successfully.
