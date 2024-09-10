# EXNO2DS

## NAME : K.GOUTHAM
## REG NO : 212223110019
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
df = pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/6404fbc6-478d-43e0-a955-3c257b35d008)

```
df.dropna(inplace=True)
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/53977879-a846-49bb-a6d0-e320bd8f4e75)

```
df.info()
```
![image](https://github.com/user-attachments/assets/02c6bf4b-ca80-4883-a416-361ef3947257)

```
df.shape
```
![image](https://github.com/user-attachments/assets/716c27b3-3cab-4918-8a2a-461617640d97)

```
df.set_index('PassengerId', inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/6668f82a-6000-4ca1-9982-fb007af60091)

```
df
```
![image](https://github.com/user-attachments/assets/3ba17dd4-b6a6-42f0-9d4f-234d3aed85be)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/84e9a7b1-5d9b-437e-8302-62840b19724c)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/5850ba12-0c0e-4736-9d8f-a2eb426c46fb)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/695071aa-1a65-43dd-8470-c8e442be4dc9)
```
import seaborn as sns
sns.countplot(data=df,x='Survived')
```
![image](https://github.com/user-attachments/assets/7a7f11eb-7062-4902-bd5c-6db71d4206c0)

```
df
```
![image](https://github.com/user-attachments/assets/43d53915-ecb8-4f64-8454-cdc37a2dc591)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/c1e8d391-6981-4af1-a075-e481123a9c0c)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/71f71032-083e-48fc-802f-957acdc2485a)

```
sns.catplot(x='Gender',col='Survived',kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/94814acb-484d-4197-b447-892df0a82d91)

```
sns. catplot(x='Survived', hue="Gender", data=df, kind = "count" )
```
![image](https://github.com/user-attachments/assets/b52085ed-24df-4936-8ef5-2e1e2357ee25)

```
sns. catplot(data=df, col = "Survived", x = "Gender", hue="Pclass", kind = "count")
```
![image](https://github.com/user-attachments/assets/adec88f0-641f-441f-a753-d0f9f3375e98)

```
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/0d057046-cccf-4ceb-868a-83d0ad7a3849)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/d24b3db7-4adc-4823-8576-c45a9a49da37)
`

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
    
