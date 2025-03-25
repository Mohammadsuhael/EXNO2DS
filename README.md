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




[1]
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/a08719b1-7729-4657-b3f5-49accf1e0945)


[2]
```
df.info()
```
![image](https://github.com/user-attachments/assets/b4ca52c0-38d6-4dad-81e2-eb2d318ba943)

[3]
```
df.shape
```
(891, 12)

[4]
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/d2b3d624-98ea-4d95-94e8-c91eb60285dc)

[5]
```
df.shape
```
(891, 11)

[6]
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/f678b4fc-70f4-45d9-87ac-9e828eab10bc)


[7]
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/3410d06c-9c62-4e25-8783-524c96a046b1)
[8]
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/393d36b2-3576-4310-9054-bf88c0fddfc0)

[9]
```
sns.countplot(data=df,x="Survived")
```
![download](https://github.com/user-attachments/assets/c7742673-dd83-46ba-a016-0be872687aa8)

[10]
```
df
```
![image](https://github.com/user-attachments/assets/d033d422-2eb1-4e1b-bb4d-38a25c1e8bcb)

[11]
```
df.Pclass.unique()
```
array([3, 1, 2])

[12]
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/8edac54e-0e23-4dcf-9b38-639acf82290b)

[13]
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![download](https://github.com/user-attachments/assets/92081c33-38c1-44eb-986c-ec1c60c6b685)

[14]
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![download](https://github.com/user-attachments/assets/8f49fbbf-f954-4fd4-ab7b-4393c4757e65)

[15]
```
df.boxplot(column="Age",by="Survived")
```
![download](https://github.com/user-attachments/assets/c766c83d-d7d6-4f99-b678-5c1fd7af3e5a)

[16]
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![download](https://github.com/user-attachments/assets/5fa11dee-199b-46c4-8b14-bfe3495bcca8)

[17]
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![download](https://github.com/user-attachments/assets/d6264af9-1991-4149-8e35-3def07418c20)

[18]
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![download](https://github.com/user-attachments/assets/b6f8b9fe-7e2f-4e5b-bd55-f43fb3bf2d77)

[19]
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![download](https://github.com/user-attachments/assets/efd9ddc0-8ce4-47fc-ae04-4112c3aae415)

[20]
```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![download](https://github.com/user-attachments/assets/2c8b4e3a-6e38-4e96-91b0-6026e9a192c8)

[21]
```
sns.pairplot(df)
```

![download](https://github.com/user-attachments/assets/6a6fe1ac-0d79-4e36-a561-83010eda2634)



# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
