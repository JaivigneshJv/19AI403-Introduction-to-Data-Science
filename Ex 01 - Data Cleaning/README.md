# Data Cleaning
## AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

## Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

Seaborn is a library for making statistical graphics in Python. It builds on top of matplotlib and integrates closely with pandas data structures.Seaborn helps you explore and understand your data. Its plotting functions operate on dataframes and arrays containing whole datasets and internally perform the necessary semantic mapping and statistical aggregation to produce informative plots. Its dataset-oriented, declarative API lets you focus on what the different elements of your plots mean, rather than on the details of how to draw them. 





## ALGORITHM
### STEP 1
Read the given Data

### STEP 2
Get the information about the data

### STEP 3
Remove the null values from the data

### STEP 4
Save the Clean data to the file

# CODE 
```
'''
Program developed by: V JAIVIGNESH
Register number: 212220040055

'''
import pandas as pd 
import numpy as ns
import seaborn as sns

df=pd.read_csv('Loan_data.csv') 
df1=pd.read_csv('Data_set.csv') #dataset.csv as df1 
print(df)
print(df1)

df.head() #.head(): Shows the first 5 rows of the dataset (you can change this number by passing an integer as a parameter)
df.tail() #.tail(): Shows the last 5 rows of the dataset (you can change this number by passing an integer as a parameter)
df.describe() #.describe(): Shows the main statistics for every numerical column in our dataset
df.info() #.info(): Shows the rows count and the types
df.shape
#We can even show the column names because we have too many and they don’t fit in the screen
df.columns
df.isnull().sum()
sns.heatmap(df.isnull(), cmap='viridis') #to view null values
df['Gender'] = df["Gender"].fillna(df['Gender'].mode()[0]) 
#NaN values in gender can be chanced to unspecified df['Gender']=df.fillna("Unspecifed") 
df['Dependents'] = df["Dependents"].fillna(df['Dependents'].mode()[0])
df['Self_Employed'] = df["Self_Employed"].fillna(df['Self_Employed'].mode()[0])
df['LoanAmount'] = df["LoanAmount"].fillna(df['LoanAmount'].mode()[0])
df['Loan_Amount_Term'] = df["Loan_Amount_Term"].fillna(df['Loan_Amount_Term'].mode()[0])
df['Credit_History'] = df["Credit_History"].fillna(df['Credit_History'].mode()[0])
df.isnull().sum()
sns.boxplot(data=df) #box plot to show distributions with respect to categories.
df.to_csv('Loan_data_cleaned.csv') #back to csv 


#for data 2
df1.head() #.head(): Shows the first 5 rows of the dataset (you can change this number by passing an integer as a parameter)
df1.tail() #.tail(): Shows the last 5 rows of the dataset (you can change this number by passing an integer as a parameter)
df1.describe() #.describe(): Shows the main statistics for every numerical column in our dataset
df1.info() #.info(): Shows the rows count and the types
df1.shape
#We can even show the column names because we have too many and they don’t fit in the screen
df1.columns
df1.isnull().sum()
sns.heatmap(df1.isnull(), cmap='viridis') #to view null values
df1['show_name'] = df1["show_name"].fillna(df1['show_name'].mode()[0]) 
#NaN values in showname can be chanced to to be declared df1['show_name']=df1.fillna("TBD") 
df1['rating'] = df1["rating"].fillna(df1['rating'].mode()[0])
df1['current_overall_rank'] = df1["current_overall_rank"].fillna(df1['current_overall_rank'].mode()[0])
df1['aired_on'] = df1["aired_on"].fillna(df1['aired_on'].mode()[0])
df1['original_network'] = df1["original_network"].fillna(df1['original_network'].mode()[0])
df1['watchers'] = df1["watchers"].fillna(df1['watchers'].mode()[0])
# various methods can be used based on our requirement (mean or median)
df1.isnull().sum()
sns.boxplot(data=df1) #box plot to show distributions with respect to categories.
df1.to_csv('Data_set_cleaned.csv') #back to csv 

# various methods can be used based on our requirement (mean or median)
```

# OUTPUT 

<img width="1151" alt="Screenshot 2023-05-20 at 8 13 03 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/36cf64fa-c383-444c-ba47-fecc73569880">
<img width="780" alt="Screenshot 2023-05-20 at 8 13 11 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/cb75162b-9a83-42ea-a4ea-807378528628">
<img width="780" alt="Screenshot 2023-05-20 at 8 13 19 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/f00a0fc9-3be2-4bcc-b100-86d82021a7a8">
<img width="780" alt="Screenshot 2023-05-20 at 8 13 24 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/34146179-5e71-410b-bbea-4a5119a124e8">
<img width="780" alt="Screenshot 2023-05-20 at 8 13 29 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/d4a2db8b-e9e7-464c-b73e-89c6f8438a58">
<img width="726" alt="Screenshot 2023-05-20 at 8 13 43 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/3fb861f7-1f5c-4667-9613-dcbe3034b27c">
<img width="726" alt="Screenshot 2023-05-20 at 8 13 52 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c257725c-8239-4988-bdf4-f170bb642441">
<img width="641" alt="Screenshot 2023-05-20 at 8 13 57 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6b139670-7b87-4c2d-a628-282dde16e189">
<img width="645" alt="Screenshot 2023-05-20 at 8 14 03 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c054b715-00cb-458d-b0e4-80c261c11945">
<img width="625" alt="Screenshot 2023-05-20 at 8 14 09 AM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/6e600293-4b56-4801-b964-8dc690eef2b5">

# Result
The given data is read and data cleaning is performed and the cleaned data is saved to a file.
