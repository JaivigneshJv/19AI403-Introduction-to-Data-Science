# Feature Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
```
NAME : V JAIVIGNESH
REG NO : 212220040055

import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns

df=pd.read_csv('/content/titanic_dataset.csv')
df.head()

df.shape

df.isnull().sum()

df.info()

df.describe()

df['Cabin']=df['Cabin'].fillna("Unknown")

df['Age'] = df["Age"].fillna(df['Age'].mean())

df['Embarked'] = df['Embarked'].fillna('S')

df.isnull().sum()


df.info()

df.plot.box(grid='True')


lower_limit,upper_limit = df.Fare.quantile([0.010, 0.990]) #1 and 99
lower_limit ,upper_limit

outliers = df[(df.Fare>upper_limit) | (df.Fare<lower_limit)]
outliers

df=df[((df['Fare']<upper_limit))&(df['Fare']>lower_limit)]

df.shape

df2=df.copy()


from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
sex=['male','female']
enc = OrdinalEncoder(categories=[sex])
df2['Sex']=enc.fit_transform(df2[["Sex"]]) #0-male 1-female

df2.head()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
embarked=['S','C','Q']
enc = OrdinalEncoder(categories=[embarked])
df2['Embarked']=enc.fit_transform(df2[["Embarked"]]) #0 S = Southampton 1 C = Cherbourg 2 Q = Queenstown

df2.head()

df3=df.copy()

le=LabelEncoder()
df3['Sex']=le.fit_transform(df3['Sex'])
df3.head()

df3['Embarked']=le.fit_transform(df3['Embarked'])
df3.head()

df4=df.copy()

ohe=OneHotEncoder(sparse=False)
enc=pd.DataFrame(ohe.fit_transform(df4[['Sex']]))
df4=pd.concat([df4,enc],axis=1)

df4.head()

ohe=OneHotEncoder(sparse=False)
enc=pd.DataFrame(ohe.fit_transform(df4[['Embarked']]))
df4=pd.concat([df4,enc],axis=1)

df.head()

```

# OUTPUT


<img width="1244" alt="Screenshot 2023-05-20 at 11 54 50 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/77158697-0571-46e0-a0f2-1cf6e6c81bc7">
<br><img width="1244" alt="Screenshot 2023-05-20 at 11 54 43 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/22a06584-b22f-439b-b622-681066467c31">
<br><img width="1268" alt="Screenshot 2023-05-20 at 11 54 36 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/e4968999-6c35-4c90-82dd-dc6cea3c6430">
<br><img width="390" alt="Screenshot 2023-05-20 at 11 54 28 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b17105b0-4d6f-4d20-83fb-1a87b61ace81">
<br><img width="507" alt="Screenshot 2023-05-20 at 11 54 24 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/db9ae9cf-774a-4199-884c-f4223e7fa660">
<br><img width="479" alt="Screenshot 2023-05-20 at 11 54 19 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/22d5538f-3b58-4a54-955b-6911f6e067da">
<br><img width="806" alt="Screenshot 2023-05-20 at 11 54 09 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/41ee21a7-9721-4116-b920-143922cf6b81">
<br><img width="432" alt="Screenshot 2023-05-20 at 11 54 01 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/23e686c1-759d-4194-95e0-e5a6219284be">
<br><img width="256" alt="Screenshot 2023-05-20 at 11 53 56 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/e7a244d6-280e-4b7b-a3e1-56a0c8148108">
<br><img width="256" alt="Screenshot 2023-05-20 at 11 53 51 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c40ba6e1-f7aa-4fd7-997d-688a6c47149e">
<br><img width="1227" alt="Screenshot 2023-05-20 at 11 53 43 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6e178894-09da-444c-8042-b6a4054f6352">


# RESULT 
Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully.


