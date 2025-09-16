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
Univariate Analysis
```

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('/content/titanic_dataset (1).csv')
df
```

<img width="1552" height="672" alt="dse 0 1" src="https://github.com/user-attachments/assets/f35a58d1-1f2e-4d7c-8827-a86b6351d551" />

```
df.info()
```

<img width="477" height="480" alt="dse 0 2" src="https://github.com/user-attachments/assets/89712ddf-3600-4880-9239-339059bf0cd1" />

```
df.dtypes
```

<img width="300" height="562" alt="dse 0 3" src="https://github.com/user-attachments/assets/c7d9f339-2baf-49b0-aeb2-b8614a0f9a8e" />

```
df.describe()
```

<img width="991" height="412" alt="dse 0 4" src="https://github.com/user-attachments/assets/e843d63b-b9d5-407b-b70b-f65210387eb1" />

```
df.value_counts()
```

<img width="1578" height="611" alt="dse 0 5" src="https://github.com/user-attachments/assets/1231514a-23fb-4396-966b-86fe4820b19a" />

```
df['Age'].value_counts()
```

<img width="296" height="595" alt="dse 0 6" src="https://github.com/user-attachments/assets/f6d02773-f0eb-4402-bcc1-5cac0897d23e" />

```
df.shape
```

<img width="213" height="97" alt="dse 0 7" src="https://github.com/user-attachments/assets/26f1d7e5-b978-4784-8e1e-d841a9196033" />

```
df.set_index('PassengerId',inplace=True)
df.describe()
```

<img width="857" height="437" alt="dse 0 8" src="https://github.com/user-attachments/assets/1ef8944a-5585-4d47-8b7a-3ebc6a52e421" />

```
df.nunique()
```

<img width="260" height="565" alt="dse 0 9" src="https://github.com/user-attachments/assets/a28ce9d3-993c-49bb-8cf9-a5f93b25b55d" />

```
sns.countplot(data=df,x='Survived')
```

<img width="793" height="640" alt="dse 0 10" src="https://github.com/user-attachments/assets/1eedc484-2cf3-4007-a124-d86b1e7d2f94" />

```
df.Pclass.unique()
```

<img width="293" height="93" alt="dse 0 11" src="https://github.com/user-attachments/assets/82b55221-a0a9-4893-be5b-720d6a561a12" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1498" height="611" alt="dse 0 12" src="https://github.com/user-attachments/assets/e516b6f3-526a-42dc-bd05-9c3139c8c52e" />

```
Bivariate Analysis
```

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="962" height="697" alt="dse 0 13" src="https://github.com/user-attachments/assets/d6177499-db2a-4063-b10d-cb734f0bb45e" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="757" height="657" alt="dse 0 14" src="https://github.com/user-attachments/assets/26281d98-c3a3-4cf8-9589-0b7701d21f1c" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="773" height="618" alt="dse 0 15" src="https://github.com/user-attachments/assets/5dd303f8-5960-401b-b8d0-f5b6ba7355bd" />

```
Multivariate Analysis
```

```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="927" height="637" alt="dse 0 16" src="https://github.com/user-attachments/assets/ef4b5179-dc63-47d6-a19c-49accb0b45e7" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="771" height="601" alt="dse 0 17" src="https://github.com/user-attachments/assets/bfc07eb5-b061-4d9f-b33b-bd7692c71629" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1377" height="703" alt="dse 0 18" src="https://github.com/user-attachments/assets/147a96f3-70fb-49ac-9cfb-2c242ff998ff" />

```
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr, annot=True)
```

<img width="726" height="632" alt="dse 0 19" src="https://github.com/user-attachments/assets/3cf6a21e-2554-4095-9358-0d03d2d84dc0" />

# RESULT
        To perform Exploratory Data Analysis on the given data set is successfully completed.
