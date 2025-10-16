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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset (1).csv")
df
```
<img width="1380" height="708" alt="Screenshot 2025-10-16 140552" src="https://github.com/user-attachments/assets/e3186fed-8366-48dd-b850-6849b3d817ce" />

```
df.info()
```
<img width="683" height="472" alt="image" src="https://github.com/user-attachments/assets/8bfbfb19-914b-4496-8f42-bf0a3f28ab95" />

```
df.describe()
```
<img width="969" height="431" alt="image" src="https://github.com/user-attachments/assets/7d7b55f2-14a1-4313-b2e3-27ed20fe3c58" />

```
df.dtypes
```
<img width="487" height="637" alt="image" src="https://github.com/user-attachments/assets/734b0e51-6c38-4fbb-8cc8-e25e5007828b" />

```
df.shape
```
<img width="297" height="101" alt="image" src="https://github.com/user-attachments/assets/f9474e68-3e40-405e-80e0-9556e5e59b28" />

```
df.value_counts()
```
<img width="1447" height="666" alt="image" src="https://github.com/user-attachments/assets/ff517546-ca71-4b69-a82c-e187e5aba8a2" />


```
df['Age'].value_counts()
```
<img width="752" height="650" alt="image" src="https://github.com/user-attachments/assets/75838e1d-c323-4e49-95d3-c5e6c33f240b" />


```
df.set_index("PassengerId",inplace=True)
df
```
<img width="1440" height="643" alt="image" src="https://github.com/user-attachments/assets/ea5ec563-a76e-4f64-a855-7986d202afe0" />


```
df.nunique
```
<img width="1131" height="284" alt="image" src="https://github.com/user-attachments/assets/5030f515-3226-4cc7-9982-8484d99ec0c1" />


```
sns.countplot(data=df,x='Survived')``
```
<img width="1009" height="632" alt="image" src="https://github.com/user-attachments/assets/538f2a2b-b6a2-4baa-bc47-f4e734c43008" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1463" height="661" alt="image" src="https://github.com/user-attachments/assets/e89aaf1e-1e07-43ee-99cc-3d6d3e55b7f0" />

```
sns.catplot(x='Gender',col='Survived',kind="count",data=df,height=5,aspect=1)
```
<img width="1456" height="699" alt="image" src="https://github.com/user-attachments/assets/951c0b0d-27b6-40de-b3f0-e49aa1a4833e" />

```
df.boxplot(column='Age',by='Survived')
df
```
<img width="1427" height="661" alt="image" src="https://github.com/user-attachments/assets/24a4939d-8715-41c2-8b07-b573122ac624" />

<img width="934" height="631" alt="image" src="https://github.com/user-attachments/assets/471f3e5d-e62d-4074-997e-b5e72cb3d14c" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="921" height="621" alt="image" src="https://github.com/user-attachments/assets/0f010903-f2e5-442e-bdef-19fbc5149656" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="977" height="608" alt="image" src="https://github.com/user-attachments/assets/2a71e62b-30e3-475f-81c7-03a3a0a86937" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```
<img width="1475" height="658" alt="image" src="https://github.com/user-attachments/assets/e1ed3147-fdd8-49b4-8092-42de55b18b9b" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="922" height="629" alt="image" src="https://github.com/user-attachments/assets/3018b28a-6125-4454-b7bd-9433bed2aba3" />


```
corr=df.select_dtypes(include=np.number).corr
sns.heatmap(corr,annot=True)
```
<img width="1027" height="643" alt="image" src="https://github.com/user-attachments/assets/85f88c11-503c-47d1-8584-0a4bb11b1fea" />




# RESULT
       THUS THE PROGRAM HAS BEEN EXECUTED SUCCESSFULY
