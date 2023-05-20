# Univariate-Analysis

### AIM
To read the given data and perform the univariate analysis with different types of plots.

### EXPLANATION

Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

### ALGORITHM

#### STEP 1

Read the given data.

#### STEP 2

Get the information about the data.

#### STEP 3

Remove the null values from the data.

#### STEP 4

Mention the datatypes from the data.

#### STEP 5

Count the values from the data.

#### STEP 6

Do plots like boxplots,countplot,distribution plot,histogram plot.

### PROGRAM
```
Name: V JAIVIGNESH
REG NO: 212220040055

import pandas as pd 
import numpy as ns
import seaborn as sns

df=pd.read_csv('SuperStore.csv') 
df.head()
df.info()
df.dtypes
for i in df.columns:
  if df[i].dtypes=='float64':
    print(df[i].value_counts())
    
df.describe()

list=[]
for i in df.columns:
  if df[i].dtypes=='float64':
    list.append(i)

sns.boxplot(data=df[list], orient="h")

sns.countplot(data=df[list], orient="h")

#https://gist.github.com/mwaskom/de44147ed2974457ad6372750bbe5751

sns.histplot(df[list])

sns.distplot(df[list])

df.skew()

df.kurtosis()

```

### OUTPUT

<img width="417" alt="Screenshot 2023-05-20 at 11 41 48 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/922d7358-6498-4d9a-9872-75ad4be62910">
<img width="417" alt="Screenshot 2023-05-20 at 11 41 45 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/32b403f2-ab20-40ec-a748-8320d01d3d80">
<img width="571" alt="Screenshot 2023-05-20 at 11 41 36 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/2cab3775-4358-403e-b019-67a87eeee985">
<img width="571" alt="Screenshot 2023-05-20 at 11 41 33 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c5858e73-a981-4583-b48f-f2aff129fc09">
<img width="571" alt="Screenshot 2023-05-20 at 11 41 30 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/42743ca2-a201-4f15-85dd-22c363c77695">
<img width="571" alt="Screenshot 2023-05-20 at 11 41 26 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/a419e323-01e6-4f60-9579-4070982ace6f">
<img width="571" alt="Screenshot 2023-05-20 at 11 41 21 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/0fc4c617-2ca0-4f09-8747-17a27c9cd121">
<img width="571" alt="Screenshot 2023-05-20 at 11 41 11 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b601571f-446b-4a98-add1-8d3582135f9f">
<img width="563" alt="Screenshot 2023-05-20 at 11 41 01 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/735aeae5-9b43-4b45-bc23-876eb791df8a">
<img width="656" alt="Screenshot 2023-05-20 at 11 40 55 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ad331405-4f2c-4f03-8831-aaeacbf5b439">
<img width="1332" alt="Screenshot 2023-05-20 at 11 40 47 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6fcd96e5-fa0e-488c-aef7-4b6d645d84e6">



### Result

Thus we have read the given data and performed the univariate analysis with different types of plots.
