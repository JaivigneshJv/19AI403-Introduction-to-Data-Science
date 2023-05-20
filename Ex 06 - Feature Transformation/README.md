# Feature Transformation

# AIM
To read the given data and perform Feature Transformation process and save the data to a file. 

# EXPLANATION
Feature Transformation is a technique by which we can boost our model performance. Feature transformation is a mathematical transformation in which we apply a mathematical formula to a particular column(feature) and transform the values which are useful for our further analysis.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Transformation techniques to all the features of the data set
### STEP 4
Save the data to the file

# CODE
```
Developed By    : V JAIVIGNESH
Register Number : 212220040055


import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import statsmodels.api as sm
import scipy.stats as stats
from sklearn.preprocessing import QuantileTransformer

df=pd.read_csv("/content/Data_to_Transform.csv")
df.head()

df.info()

df.describe()

df.isnull().sum()

df.shape

df.columns

df.duplicated()

sm.qqplot(df['Highly Positive Skew'],fit=True,line='45')
plt.show()


sm.qqplot(df['Highly Negative Skew'],fit=True,line='45')
plt.show()


sm.qqplot(df['Moderate Positive Skew'],fit=True,line='45')
plt.show()


sm.qqplot(df['Moderate Negative Skew'],fit=True,line='45')
plt.show()


df['Highly Positive Skew'] = np.log(df['Highly Positive Skew'])
sm.qqplot(df['Highly Positive Skew'],fit=True,line='45')
plt.show()


df['Moderate Positive Skew'] = np.log(df['Moderate Positive Skew'])
sm.qqplot(df['Moderate Positive Skew'],fit=True,line='45')
plt.show()

df['Highly Positive Skew'] = 1/df['Highly Positive Skew']
sm.qqplot(df['Highly Positive Skew'],fit=True,line='45')
plt.show()


df['Highly Positive Skew'] = df['Highly Positive Skew']**(1/1.2)
sm.qqplot(df['Highly Positive Skew'],fit=True,line='45')
plt.show()


df['Moderate Positive Skew_1'], parameters=stats.yeojohnson(df['Moderate Positive Skew'])
sm.qqplot(df['Moderate Positive Skew_1'],fit=True,line='45')
plt.show()


from sklearn.preprocessing import PowerTransformer
transformer=PowerTransformer("yeo-johnson")
df['ModerateNegativeSkew_2']=pd.DataFrame(transformer.fit_transform(df[['Moderate Negative Skew']]))
sm.qqplot(df['ModerateNegativeSkew_2'],fit=True,line='45')
plt.show()


from sklearn.preprocessing import QuantileTransformer
qt = QuantileTransformer(output_distribution = 'normal')
df['ModerateNegativeSkew_2'] = pd.DataFrame(qt.fit_transform(df[['Moderate Negative Skew']]))
sm.qqplot(df['ModerateNegativeSkew_2'],fit=True,line='45')
plt.show()

```
# OUPUT


<img width="575" alt="Screenshot 2023-05-20 at 12 11 46 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/1b04a4db-1407-498a-8d9b-e0308cd69f3c">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 40 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/7dbedea1-f174-4fb3-8810-d2fd62534b90">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 36 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/7fb291ea-413f-4523-8c0b-e0dbf2856ff3">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 33 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/98b02632-29fc-46c7-83d9-81c7a1447819">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 29 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/68d75c91-9336-4258-9250-d9fa80d4e3a4">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 26 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/652b5a10-9827-40fa-94b3-d22177a3db13">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 23 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ee71845c-1943-42d8-a916-7b824a666072">
<img width="575" alt="Screenshot 2023-05-20 at 12 11 20 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ca084799-6cf9-4168-b495-705084005fd8">
<img width="568" alt="Screenshot 2023-05-20 at 12 11 15 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6b49f205-0c7e-4142-851e-c779c9c646bd">
<img width="375" alt="Screenshot 2023-05-20 at 12 11 10 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/a8ffc7d3-6cdd-42e6-b42a-f46df93b806b">
<img width="811" alt="Screenshot 2023-05-20 at 12 11 04 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ad6a4119-bd58-4d70-bd80-6926d10a1ca4">
<img width="1025" alt="Screenshot 2023-05-20 at 12 10 58 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/9af7f889-1ee7-45ba-9a95-20712afeb2d0">
<img width="1244" alt="Screenshot 2023-05-20 at 12 10 50 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/66d99df3-b8dd-49cf-b7ec-52f0e59ae838">
<img width="1244" alt="Screenshot 2023-05-20 at 12 10 46 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c8edaa21-810f-4627-bc11-ca5a46d77021">


# RESULT 
Thus the Feature Transformation for the given datasets had been executed successfully
