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
dt=pd.read_csv("C:/Users/admin/Downloads/titanic_dataset.csv")
dt
```
<img width="1347" height="561" alt="image" src="https://github.com/user-attachments/assets/51a678f5-399a-4573-92df-a3526ed99b43" />
```
dt.info()
```
<img width="1226" height="410" alt="image" src="https://github.com/user-attachments/assets/c68ff273-2516-4b34-8f3f-205ec24f8068" />
```
dt.shape
```
<img width="1013" height="38" alt="image" src="https://github.com/user-attachments/assets/b931435b-5613-4b80-9243-872bab4e1dd8" />
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
<img width="1298" height="360" alt="image" src="https://github.com/user-attachments/assets/32e10b29-4cf6-449f-a382-ae9d3a879887" />

```
dt.nunique()
```
<img width="1183" height="260" alt="image" src="https://github.com/user-attachments/assets/3b68e60c-e885-4bd5-be52-cbd07721af4c" />
```
dt["Survived"].value_counts()
```

<img width="1271" height="89" alt="image" src="https://github.com/user-attachments/assets/d096d6e4-d6f1-4734-9bfa-2f4404de6f97" />
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
<img width="1366" height="96" alt="image" src="https://github.com/user-attachments/assets/350ec2c2-db78-4ada-a78f-779611d9980a" />
```
sns.countplot(data=dt,x="Survived")

```

<img width="1287" height="577" alt="image" src="https://github.com/user-attachments/assets/9c9ecfcd-a5a1-42b9-a820-4a3a1673966d" />

```
dt.Pclass.unique()
```
<img width="844" height="47" alt="image" src="https://github.com/user-attachments/assets/bec36c6f-8616-45c1-ba79-b8dcb2d1f2e2" />
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
<img width="1340" height="557" alt="image" src="https://github.com/user-attachments/assets/174a10f6-ae5e-4afa-9521-907fe079584c" />
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="1242" height="656" alt="image" src="https://github.com/user-attachments/assets/c32c9f44-f183-41df-8662-ccbf487231cb" />

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
<img width="1346" height="641" alt="image" src="https://github.com/user-attachments/assets/1262fe2b-9dad-4bd8-bb5a-0405c5ac7953" />
```
dt.boxplot(column="Age",by="Survived")
```
<img width="1267" height="614" alt="image" src="https://github.com/user-attachments/assets/9dcc59cd-064a-4f27-b01f-e26022708cd3" />
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
<img width="1340" height="766" alt="image" src="https://github.com/user-attachments/assets/6429b25e-26bb-4c81-b896-a49093fb1d35" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
<img width="1021" height="571" alt="image" src="https://github.com/user-attachments/assets/da1974de-a26e-4ace-9de9-e6ce68b23713" />
```
fig,ax1=plt.subplots (figsize=(8,5))

sns.boxplot(ax=ax1,x="Pclass", y="Age", hue="Gender", data=dt)
```
<img width="1175" height="583" alt="image" src="https://github.com/user-attachments/assets/d5e1cceb-19d8-4f06-b497-8cb8ac5c536a" />
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1132" height="570" alt="image" src="https://github.com/user-attachments/assets/d371b1f6-f362-49f8-941f-df6e8ba8aa1b" />
```
corr = dt.select_dtypes(include='number').corr()
sns.heatmap(corr, annot=True)
```
<img width="1082" height="555" alt="image" src="https://github.com/user-attachments/assets/214df2a0-d4dc-42d7-a9b0-66019eb9dec8" />

```
sns.pairplot(dt)
```
<img width="1372" height="884" alt="image" src="https://github.com/user-attachments/assets/0fce2d4e-b291-48d4-bf10-e52d73398fe0" />



# RESULT
       
Thus the Exploratory  Data Analysis on The Given Data Set Was Performed Sucessfully.
