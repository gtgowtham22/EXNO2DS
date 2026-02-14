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
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("titanic_dataset.csv")
dt
```

<img width="754" height="439" alt="image" src="https://github.com/user-attachments/assets/49735883-584a-4d9f-a62f-e13efd17f598" />

```
dt.info()
```
<img width="348" height="314" alt="image" src="https://github.com/user-attachments/assets/48504a4a-beeb-4f8a-bddd-483549e49daa" />

```
dt.shape
```
<img width="103" height="29" alt="image" src="https://github.com/user-attachments/assets/b062b6e6-0d8c-4b26-82f5-df59819578e6" />

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
<img width="508" height="227" alt="image" src="https://github.com/user-attachments/assets/570e1858-6877-41c5-8888-49e534405e50" />

```
dt.nunique()
```
<img width="153" height="211" alt="image" src="https://github.com/user-attachments/assets/35e6b723-df87-4346-aff3-6eadb96ec269" />

```
dt["Survived"].value_counts()
```
<img width="307" height="52" alt="image" src="https://github.com/user-attachments/assets/bbedbb37-0d4a-48d7-ba76-098ecaf88c44" />

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
<img width="289" height="64" alt="image" src="https://github.com/user-attachments/assets/a27246d5-4776-424a-960e-834f21c42d68" />

```
sns.countplot(data=dt,x="Survived")
```
<img width="586" height="450" alt="image" src="https://github.com/user-attachments/assets/2234b02e-9dc0-43d1-90e2-ddc34b07eb01" />

```
dt
```
<img width="739" height="423" alt="image" src="https://github.com/user-attachments/assets/dca290f9-57a4-46fc-b037-9dfe9a44f6dd" />

```
dt.Pclass.unique()
```
<img width="235" height="25" alt="image" src="https://github.com/user-attachments/assets/effa812d-e24c-4ce1-b598-fe8f7e2b285b" />

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
<img width="746" height="409" alt="image" src="https://github.com/user-attachments/assets/36c6b9ba-fc9e-4550-bd18-8edcd778e07b" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="699" height="502" alt="image" src="https://github.com/user-attachments/assets/bddb952d-6496-4378-a2ff-04a467d3f839" />


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
<img width="650" height="508" alt="image" src="https://github.com/user-attachments/assets/af7afde5-8986-401f-9f8e-c783aa1e6df5" />

```
dt.boxplot(column="Age",by="Survived")
```
<img width="571" height="471" alt="image" src="https://github.com/user-attachments/assets/f046a96c-e4c0-4b55-a4f3-932925aed86c" />

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
<img width="599" height="450" alt="image" src="https://github.com/user-attachments/assets/d22c106d-fce0-4063-ac14-8384f2ec86fe" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
<img width="649" height="596" alt="image" src="https://github.com/user-attachments/assets/7ebdaa44-51d6-4960-a50a-d6043148f138" />

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
<img width="691" height="460" alt="image" src="https://github.com/user-attachments/assets/a38ae024-13a1-4e97-8c71-372843e3ab2c" />

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="752" height="381" alt="image" src="https://github.com/user-attachments/assets/a408df26-eaa8-4f30-ac3a-4650e0bf7e86" />

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
<img width="578" height="443" alt="image" src="https://github.com/user-attachments/assets/516fbb2e-e62d-4d47-bfcc-5ea836131924" />

```
sns.pairplot(dt)
```
<img width="836" height="852" alt="image" src="https://github.com/user-attachments/assets/b83763c3-f7ed-4f0c-a312-0410b0d44bf6" />


# RESULT
Thus,the Exploratory Data Analysis on the given data set was performed successfully.
