# Multivariate Analysis

## Aim
To perform Multivariate EDA on the given data set.

##Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## Algorithm

### Step1
Import the built libraries required to perform EDA and outlier removal.

### Step2
Read the given csv file.

### Step3
Convert the file into a dataframe and get information of the data.

### Step4
Return the objects containing counts of unique values using (value_counts()).

### Step5
Plot the counts in the form of Histogram or Bar Graph.

### Step6
Use seaborn the bar graph comparison of data can be viewed.

### Step7
Find the pairwise correlation of all columns in the dataframe.corr()

### Step8
Save the final data set into the file.

## Code

```
NAME : V JAIVIGNESH
REG NO: 212220040055

import pandas as pd 
import numpy as ns
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv('SuperStore.csv') 
df.head()
df.info()
df.dtypes
list=[]
for i in df.columns:
  if df[i].dtypes=='float64':
    list.append(i)

sns.scatterplot(data=df[list])
sns.barplot(data=df[list])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
df.corr()
sns.heatmap(df.corr(),annot=True)

```

## Output
<img width="536" alt="Screenshot 2023-05-20 at 11 47 14 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/a924f5b1-34a8-4df3-9768-f73411da260c">
<img width="561" alt="Screenshot 2023-05-20 at 11 47 08 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/64100ec5-0730-410a-80ff-27ed4e799e67">
<img width="1077" alt="Screenshot 2023-05-20 at 11 47 01 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/2755e80a-308b-439d-90d7-75a27c3a2b2b">
<img width="527" alt="Screenshot 2023-05-20 at 11 46 48 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/f772a87d-c9bf-4f00-8376-0891f8d8f884">
<img width="527" alt="Screenshot 2023-05-20 at 11 46 45 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/5a9321b8-f982-44d1-a650-5347b3dc5f86">
<img width="522" alt="Screenshot 2023-05-20 at 11 46 38 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/08d06c5b-dd3e-4e06-9d36-f84fd76fc14d">
<img width="570" alt="Screenshot 2023-05-20 at 11 46 31 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/d8fcefeb-e824-4ca4-b755-ebca7307eed7">
<img width="1350" alt="Screenshot 2023-05-20 at 11 46 25 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/cf58f37c-ec73-4de6-aa80-00d9d1de4682">




## Result
Thus the program to perform EDA on the given data set is successfully executed.
