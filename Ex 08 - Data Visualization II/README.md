# Data Visualization II

## AIM:

To Perform Data Visualization on a complex dataset and save the data to a file. 

## EXPLANATION:

Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM:

### STEP 1:
Read the given Data.
### STEP 2:
Clean the Data Set using Data Cleaning Process.
### STEP 3:
Apply Feature generation and selection techniques to all the features of the data set.
### STEP 4:
Apply data visualization techniques to identify the patterns of the data.

## CODE:
```
NAME   : V JAIVIGNESH
REG NO : 212220040055

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
df=pd.read_csv("Superstore.csv")
df

df.drop('Row ID',axis=1,inplace=True)
df.drop('Order ID',axis=1,inplace=True)
df.drop('Customer ID',axis=1,inplace=True)
df.drop('Customer Name',axis=1,inplace=True)
df.drop('Country',axis=1,inplace=True)
df.drop('Postal Code',axis=1,inplace=True)
df.drop('Product ID',axis=1,inplace=True)
df.drop('Product Name',axis=1,inplace=True)
df.drop('Order Date',axis=1,inplace=True)
df.drop('Ship Date',axis=1,inplace=True)
print("Updated dataset")
df

df.isnull().sum()

plt.figure(figsize=(12,10))
plt.title("Data with outliers")
df.boxplot()
plt.show()
plt.figure(figsize=(12,10))

cols = ['Sales','Quantity','Discount','Profit']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()


#line plots
import seaborn as sns
sns.lineplot(x="Sub-Category",y="Sales",data=df,marker='o')
plt.title("Sub Categories vs Sales")
plt.xticks(rotation = 90)
plt.show()


sns.lineplot(x="Category",y="Profit",data=df,marker='o')
plt.xticks(rotation = 90)
plt.title("Categories vs Profit")
plt.show()


sns.lineplot(x="Region",y="Sales",data=df,marker='o')
plt.xticks(rotation = 90)
plt.title("Region area vs Sales")
plt.show()


sns.lineplot(x="Category",y="Discount",data=df,marker='o')
plt.title("Categories vs Discount")
plt.show()


sns.lineplot(x="Sub-Category",y="Quantity",data=df,marker='o')
plt.xticks(rotation = 90)
plt.title("Sub Categories vs Quantity")
plt.show()


#bar plots
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.title("Sub Categories vs Sales")
plt.xticks(rotation = 90)
plt.show()

sns.barplot(x="Category",y="Profit",data=df)
plt.title("Categories vs Profit")
plt.show()


sns.barplot(x="Sub-Category",y="Quantity",data=df)
plt.title("Sub Categories vs Quantity")
plt.xticks(rotation = 90)
plt.show()


sns.barplot(x="Category",y="Discount",data=df)
plt.title("Categories vs Discount")
plt.show()

sns.barplot(x="State",y="Sales",data=df)
plt.title("States vs Sales")
plt.xticks(rotation = 90)
plt.show()

sns.barplot(x="State",y="Sales",hue="Region",data=df)
plt.title("State vs Sales based on Region")
plt.xticks(rotation = 90)
plt.show()

#Histogram
sns.histplot(data = df,x = 'Region',hue='Ship Mode')
sns.histplot(data = df,x = 'Category',hue='Quantity')
sns.histplot(data = df,x = 'Sub-Category',hue='Category')
plt.xticks(rotation = 90)
plt.show()

sns.histplot(data = df,x = 'Quantity',hue='Segment')
plt.hist(data = df,x = 'Profit')
plt.show()


#count plot
plt.figure(figsize=(10,7))
sns.countplot(x ='Segment', data = df,hue = 'Sub-Category')

sns.countplot(x ='Category', data = df,hue='Discount')

sns.countplot(x ='Ship Mode', data = df,hue = 'Quantity')

sns.countplot(x ='Region', data = df,hue = 'Segment')

#Barplot
sns.boxplot(x="Sub-Category",y="Discount",data=df)
plt.xticks(rotation = 90)
plt.show()


sns.boxplot( x="Profit", y="Category",data=df)
plt.xticks(rotation = 90)
plt.show()

sns.boxplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
plt.show()


sns.boxplot(x="Category",y="Profit",data=df)

sns.boxplot(x="Region",y="Sales",data=df)
plt.figure(figsize=(10,7))
plt.show()

sns.boxplot(x="Sub-Category",y="Quantity",data=df)
plt.xticks(rotation = 90)

#KDE plot
sns.kdeplot(x="Profit", data = df,hue='Category')

sns.kdeplot(x="Sales", data = df,hue='Region')

sns.kdeplot(x="Quantity", data = df,hue='Segment')

sns.kdeplot(x="Discount", data = df,hue='Segment')

#violin plot
sns.violinplot(x="Profit",data=df)

sns.violinplot(x="Discount",y="Ship Mode",data=df)

sns.violinplot(x="Quantity",y="Ship Mode",data=df)

sns.pointplot(x=df["Quantity"],y=df["Discount"])

sns.pointplot(x=df["Quantity"],y=df["Category"])

sns.pointplot(x=df["Sales"],y=df["Sub-Category"])

df.groupby(['Category']).sum().plot(kind='pie',y='Discount',figsize=(6,10),pctdistance=1.7,labeldistance=1.2)
df.groupby(['Sub-Category']).sum().plot(kind='pie',y='Sales',figsize=(10,10),pctdistance=1.7,labeldistance=1.2)
df.groupby(['Region']).sum().plot(kind='pie',y='Profit',figsize=(6,9),pctdistance=1.7,labeldistance=1.2)
df.groupby(['Ship Mode']).sum().plot(kind='pie',y='Quantity',figsize=(8,11),pctdistance=1.7,labeldistance=1.2)
df1=df.groupby(by=["Category"]).sum()
labels=[]
for i in df1.index:
 labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df1["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()


labels=[]
for i in df1.index:
 labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df4=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
le=LabelEncoder()
ohe=OneHotEncoder
oe=OrdinalEncoder()
df4["Ship Mode"]=oe.fit_transform(df[["Ship Mode"]])
df4["Segment"]=oe.fit_transform(df[["Segment"]])
df4["City"]=le.fit_transform(df[["City"]])
df4["State"]=le.fit_transform(df[["State"]])
df4['Region'] = oe.fit_transform(df[['Region']])
df4["Category"]=oe.fit_transform(df[["Category"]])
df4["Sub-Category"]=le.fit_transform(df[["Sub-Category"]])

#scaling
from sklearn.preprocessing import RobustScaler
sc=RobustScaler()
df5=pd.DataFrame(sc.fit_transform(df4),columns=['Ship Mode', 'Segment', 'City','State','Region', 'Category','SubCategory','Sales','Quantity','Discount','Profit'])

#Heatmap
plt.subplots(figsize=(12,7))
sns.heatmap(df5.corr(),cmap="PuBu",annot=True)
plt.show()

```
## OUTPUT:

<img width="725" alt="Screenshot 2023-05-20 at 12 32 41 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/2fd244d2-0b19-4b26-bc38-5d816e333b61">
<img width="399" alt="Screenshot 2023-05-20 at 12 32 30 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/99b671da-655a-48f9-a15c-15b1cf9372f9">
<img width="496" alt="Screenshot 2023-05-20 at 12 32 22 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/fa261c63-8065-48f4-a294-92fa8ea615a7">
<img width="496" alt="Screenshot 2023-05-20 at 12 32 15 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/956f53d0-bcd8-4935-9e38-eaba41b7b23e">
<img width="496" alt="Screenshot 2023-05-20 at 12 32 12 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b6aee9c0-db75-4289-a97a-1cf43390e8df">
<img width="496" alt="Screenshot 2023-05-20 at 12 32 08 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/8b69e488-33e4-4850-8ce4-7855ed6254a9">
<img width="496" alt="Screenshot 2023-05-20 at 12 32 04 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b511d00c-964c-464c-9f82-da60c7a48b47">
<img width="496" alt="Screenshot 2023-05-20 at 12 28 40 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/531db7cd-86b3-4f61-b092-0c30b3f9025f">
<img width="496" alt="Screenshot 2023-05-20 at 12 28 37 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/f3b5c4a0-dd19-48d8-be99-ec9689826a91">
<img width="521" alt="Screenshot 2023-05-20 at 12 28 32 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/cf31b8fd-1677-4281-b438-d07dc83a0e8f">
<img width="521" alt="Screenshot 2023-05-20 at 12 28 29 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/212bfbba-a74e-4e59-84f3-99023aaae1ab">
<img width="521" alt="Screenshot 2023-05-20 at 12 28 25 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ca03f293-1b98-4aa5-9b77-e36f51c7cc61">
<img width="521" alt="Screenshot 2023-05-20 at 12 28 20 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/90cc36a5-7a25-41d5-baf7-1364bd4e982c">
<img width="521" alt="Screenshot 2023-05-20 at 12 28 17 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c23d755f-0a5b-4ff4-9948-e8bc64a1ff1d">
<img width="653" alt="Screenshot 2023-05-20 at 12 28 12 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/085fec2a-b763-4b30-a9b4-5dd925a8d0cb">
<img width="437" alt="Screenshot 2023-05-20 at 12 28 08 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/9145343c-dc38-494c-8547-a401ea710e2d">
<img width="446" alt="Screenshot 2023-05-20 at 12 28 02 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/711b61c8-1527-4b0a-84d1-b29ade6473aa">
<img width="479" alt="Screenshot 2023-05-20 at 12 27 56 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/07d900f5-ada0-4b7b-9c68-e43ecb8cdf85">
<img width="479" alt="Screenshot 2023-05-20 at 12 27 52 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/3a8df81f-3099-43c3-920a-c99c3bcc4d99">
<img width="450" alt="Screenshot 2023-05-20 at 12 27 42 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/0ecd29e5-e1fb-4690-86f9-666a8c52dc6b">
<img width="464" alt="Screenshot 2023-05-20 at 12 27 35 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c81b5d52-4e99-40bf-8faf-23ab7a61998c">
<img width="464" alt="Screenshot 2023-05-20 at 12 27 32 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/fcc8c76c-3c94-4207-af17-39a1343888c5">


## RESULT:

Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
