# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![Screenshot 2024-11-12 231127](https://github.com/user-attachments/assets/98ed47e2-418a-4937-82af-efdbf9de2e1d)


```
df = sns.load_dataset("tips")
df
```
![Screenshot 2024-11-12 231204](https://github.com/user-attachments/assets/24ef2365-98ed-461f-bf69-45ad478ba234)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![Screenshot 2024-11-12 231241](https://github.com/user-attachments/assets/9730a761-e664-491f-bcc2-310552860d9b)

```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![Screenshot 2024-11-12 231320](https://github.com/user-attachments/assets/fce74e2c-006f-480b-b598-7df0e482d7a2)

```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![Screenshot 2024-11-12 231402](https://github.com/user-attachments/assets/89602123-cd93-4636-ba2e-8bb9f3e3a163)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![Screenshot 2024-11-12 231436](https://github.com/user-attachments/assets/03267ad5-5327-4619-b85c-dffcab9cfddb)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![Screenshot 2024-11-12 231518](https://github.com/user-attachments/assets/0d4d568a-f621-4206-8ee1-e84c0c83c004)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![Screenshot 2024-11-12 231605](https://github.com/user-attachments/assets/76905c24-c8e7-4ad9-a571-820b37d86596)

```
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![Screenshot 2024-11-12 231812](https://github.com/user-attachments/assets/5c2175ed-4df9-4920-a011-26dc479423fb)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```
![Screenshot 2024-11-12 231917](https://github.com/user-attachments/assets/01aa4b10-fd24-4420-9c01-3269d9db628d)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![Screenshot 2024-11-12 231951](https://github.com/user-attachments/assets/e0f2f37f-2b6a-417e-a021-a5150ee749ef)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![Screenshot 2024-11-12 232027](https://github.com/user-attachments/assets/316340b3-0764-4ffc-8b77-b700b96cbd32)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![Screenshot 2024-11-12 232102](https://github.com/user-attachments/assets/117fc181-6926-4e3e-a8c8-543c8cab8e3c)

```
sns.histplot(data = num_var, kde = True)
```
![Screenshot 2024-11-12 232129](https://github.com/user-attachments/assets/377d169d-3f9d-4973-a4ea-d109bb45af9d)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![Screenshot 2024-11-12 232201](https://github.com/user-attachments/assets/04f5559c-36b5-4fd7-a7af-33a94e3c43de)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![Screenshot 2024-11-12 232231](https://github.com/user-attachments/assets/fe1fcc02-a06f-40d1-affd-36ce2ee80332)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![Screenshot 2024-11-12 232257](https://github.com/user-attachments/assets/0479a77a-32cd-4bbf-a4cb-763f2bd703ce)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![Screenshot 2024-11-12 232323](https://github.com/user-attachments/assets/71aa633a-af96-418d-ad93-74ed132df1e9)

```
mart=pd.read_csv("titanic_dataset.csv")
mart
```
![Screenshot 2024-11-12 232357](https://github.com/user-attachments/assets/ef9f2c13-689b-42e9-9321-99f14252e6f0)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
![Screenshot 2024-11-12 232425](https://github.com/user-attachments/assets/24eef387-2a55-4acf-a366-669671126546)

```
sns.kdeplot(data=mart,x='PassengerId')
```
![Screenshot 2024-11-12 232455](https://github.com/user-attachments/assets/6e5c011b-e7e9-4a63-a091-9503d4db0911)

```
sns.kdeplot(data=mart,x='Age')
```
![Screenshot 2024-11-12 232530](https://github.com/user-attachments/assets/e1f2e97e-f885-4737-b2cd-4698153d0740)

```
sns.kdeplot(data=mart)
```
![Screenshot 2024-11-12 232606](https://github.com/user-attachments/assets/a5da06dc-eeb9-45bd-8a93-785285b40c1e)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![Screenshot 2024-11-12 232633](https://github.com/user-attachments/assets/220e392a-6336-428e-abe4-f8975cfb43c0)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![Screenshot 2024-11-12 232702](https://github.com/user-attachments/assets/bf6782cf-1ccc-486a-8483-10cf5466466f)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![Screenshot 2024-11-12 232731](https://github.com/user-attachments/assets/3b8c715a-03c0-483d-a326-5bc2c6bd097b)

```
hm=sns.heatmap(data=data)
```
![Screenshot 2024-11-12 232755](https://github.com/user-attachments/assets/631477f1-f8d9-4ef8-8aa5-e2f077552f41)


# Result:

Thus, all the data visualization techniques of seaborn has been implemented.
