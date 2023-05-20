# Outlier Detection and Removal

## AIM

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR 

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

    (i) Using IQR detect weight outliers and print them

    (ii) Using IQR, detect height outliers and print them


## EXPERIMENT

An Outlier is an observation in a given dataset that lies far from the rest of the observations. That means an outlier is vastly larger or smaller than the remaining values in the set. An outlier is an observation of a data point that lies an abnormal distance from other values in a given population. (odd man out).Outliers badly affect mean and standard deviation of the dataset. These may statistically give erroneous results.Most machine learning algorithms do not work well in the presence of outlier. So it is desirable to detect and remove outliers.Outliers are highly useful in anomaly detection like fraud detection where the fraud transactions are very different from normal transactions.


## ALGORITHM

1. Read the given Data
2. Get the information about the data
3. Detect the Outliers using IQR method and Z score
4. Remove the outliers
5. Plot the datas using Box Plot

## PROGRAM

```
NAME : V JAIVIGNESH
REG NO: 212220040055

import pandas as pd
import numpy as np

df=pd.read_csv('Book1.csv') #given dataset

print(df)

shape

lower_limit,upper_limit = df.Data.quantile([0.010, 0.990]) #1 and 99
lower_limit ,upper_limit

outliers = df[(df.Data>upper_limit) | (df.Data<lower_limit)]
outliers

from scipy import stats
#z-score
z=np.abs(stats.zscore(df.Data))
df1=df[(z>3)]

print(df1)

df.shape[0]-df1.shape[0]

#IQR

q1=df['Data'].quantile(0.25)

q3=df['Data'].quantile(0.75)

IQR=q3-q1

df_new=df[((df['Data']<=(q1-1.5*IQR))|(df['Data']>=(q3+1.5*IQR)))]

df_new #print outliers

```
## Output 

<img width="625" alt="Screenshot 2023-05-20 at 8 28 54 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/44f3728f-179d-497f-80d1-2b708f7b8df5">
<img width="344" alt="Screenshot 2023-05-20 at 8 29 04 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ff203921-de79-4673-9a41-1167ab786899">
<img width="344" alt="Screenshot 2023-05-20 at 8 29 09 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/83c4bb7c-60ce-4b46-aebb-463770fe6d35">
<img width="344" alt="Screenshot 2023-05-20 at 8 29 14 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/a9e99885-e0b9-449f-9009-a9196bd442ce">
<img width="344" alt="Screenshot 2023-05-20 at 8 29 19 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/d9602312-87bc-4081-a3da-deb96464adeb">
<img width="195" alt="Screenshot 2023-05-20 at 8 29 27 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/003a45d8-b5f8-4a2e-8ff9-c2e035fda5c1">


## RESULT
The given datasets are read and outliers are detected and are removed using IQR and z-score methods.
