# Feature-Generation


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
REG NO: 212220040055

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

<img width="1244" alt="Screenshot 2023-05-20 at 11 54 50 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/a7bccb44-73a4-4b4a-8d27-b8090baeb01a">
<br><img width="1244" alt="Screenshot 2023-05-20 at 11 54 43 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6e50a440-36e9-4070-a6f8-85242227b830">
<br><img width="1268" alt="Screenshot 2023-05-20 at 11 54 36 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/8f8652ea-7249-4cb0-a8b6-80a2eaaf9e71">
<br><img width="390" alt="Screenshot 2023-05-20 at 11 54 28 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b4831718-c40a-4437-bede-a806535eb0b8">
<br><img width="507" alt="Screenshot 2023-05-20 at 11 54 24 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/88f270b2-3a03-43d2-aa67-96d69140e6df">
<br><img width="479" alt="Screenshot 2023-05-20 at 11 54 19 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/1bba9130-d82a-4256-a460-7d09b008e996">
<br><img width="806" alt="Screenshot 2023-05-20 at 11 54 09 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b481450d-897f-4345-b9eb-28e9cb1a18f0">
<br><img width="432" alt="Screenshot 2023-05-20 at 11 54 01 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6738e7bf-17c1-4031-b541-a5b8cea064ee">
<br><img width="256" alt="Screenshot 2023-05-20 at 11 53 56 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/3f25d501-2d9f-4132-8870-5e4752ede627">
<br><img width="256" alt="Screenshot 2023-05-20 at 11 53 51 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/8b74b0a0-b352-43ef-98c8-e3392c1af2db">
<br><img width="1227" alt="Screenshot 2023-05-20 at 11 53 43 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/f89b021b-54d0-4d18-a878-66c7bb568c52">


# RESULT 
Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully.


