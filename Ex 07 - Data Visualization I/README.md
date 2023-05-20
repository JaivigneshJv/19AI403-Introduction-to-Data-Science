# Data Visualization I

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

df = pd.read_csv('/content/Superstore.csv')
df.head()

import seaborn as sns
from matplotlib import pyplot as plt

#line plot
plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')

plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)


sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#scatterplot
sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))

sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#Boxplot
sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)

#Barplot
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#Pointplot
sns.pointplot(x=df["Quantity"],y=df["Discount"])

#Count plot
sns.countplot(x="Category",data=df)


sns.countplot(x="Sub-Category",data=df)

#Histogram
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')


#KDE Plot
sns.kdeplot(x="Profit", data = df,hue='Category')


#Plot
plt.plot(df['Category'], df['Sales'])
plt.show()


#Heatmap
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#Piechart
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
 labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()
df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
 labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#Histogram
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()


#Bargraph
plt.bar(df.index,df['Category'])
plt.show()


#Scatterplot
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 

#Boxplot
plt.boxplot(x="Sales",data=df)
plt.show()

```
## OUTPUT:

<img width="642" alt="Screenshot 2023-05-20 at 12 19 51 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/ce45231e-91cc-461c-92a4-96e24b349d59">
<img width="642" alt="Screenshot 2023-05-20 at 12 19 46 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/d9871fcd-d34e-40f8-b4b8-b547aaf97109">
<img width="642" alt="Screenshot 2023-05-20 at 12 19 42 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/af780441-e7bc-4bb3-a98d-968df3502a00">
<img width="642" alt="Screenshot 2023-05-20 at 12 19 29 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/197e2902-dd0b-4ac0-bf73-654de2837e38">
<img width="723" alt="Screenshot 2023-05-20 at 12 19 19 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/d0740921-e049-4ff0-986c-02e6a600eb0a">
<img width="511" alt="Screenshot 2023-05-20 at 12 19 13 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/776cd086-9959-4ec6-8ed8-ed872a0f861e">
<img width="510" alt="Screenshot 2023-05-20 at 12 19 10 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/5cd85c05-ad09-41a9-8c0d-3ba586b1df17">
<img width="523" alt="Screenshot 2023-05-20 at 12 19 04 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/e946d872-9319-4497-beeb-fc4f3184029d">
<img width="522" alt="Screenshot 2023-05-20 at 12 19 00 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/8bd8cfbf-bbbe-4a39-94ef-86735d038f91">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 56 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/1ae19ba7-e05e-487b-8931-3299893e113b">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 54 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/4b153d89-77f3-4063-bd54-aaa7c761248e">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 51 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/c681ffaa-9da5-4745-9495-5f1244beca7e">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 48 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/cfbe9d40-e0a5-411a-be42-4bf5aea098c1">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 45 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/4428be6e-21bb-4f59-99a9-f62d7c7bd6b1">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 42 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/7c319874-c91a-444c-a6b3-385150c36c86">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 39 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/d148ee2e-55cb-4675-92ae-ac436d6334b6">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 35 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/1f564bad-bdee-41fe-9313-a182c1fd2293">
<img width="522" alt="Screenshot 2023-05-20 at 12 18 32 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/105dbfe1-e904-4086-96b6-85709926c19c">
<img width="530" alt="Screenshot 2023-05-20 at 12 18 26 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/0b32623f-28fe-464c-b564-0398673b07e7">
<img width="551" alt="Screenshot 2023-05-20 at 12 18 21 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/64ab7fe9-413c-4fba-9353-cb39ddfe457a">
<img width="551" alt="Screenshot 2023-05-20 at 12 18 17 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/b761b459-bff9-4b38-81fa-11fa68a41a0b">
<img width="1370" alt="Screenshot 2023-05-20 at 12 18 09 PM" src="https://github.com/JaivigneshJv/19AI403-Introduction-to-Data-Science/assets/71516398/4e120ccc-dd2b-49f1-adc9-8ee92480b8f1">


## RESULT:

Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
