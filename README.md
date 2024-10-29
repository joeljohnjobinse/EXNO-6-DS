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
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/a7974812-5317-4fb1-bbaf-86a9166ed0bb)

```
df=sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/99f689b0-e5c2-4fb5-8b10-db7084e483b4)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/0b74a3ac-ea2a-4da1-bd84-1f149dd9b8c9)

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
![image](https://github.com/user-attachments/assets/2f444c64-b55e-4b53-a710-e1a9f4d35cf3)

```
import seaborn as sns
import matplotlib.pyplot as plt
#Load the tips dataset
tips=sns.load_dataset('tips')
#Calculate the average total bill and tip for each day of the week
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')
#Set the labels and title
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/b59946a5-5e23-4419-884a-4cb8e3523110)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/5763b603-f259-4944-924d-4b3d4dc010e7)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/04c4088e-fe83-46f0-bbc9-048a4445990d)

```
import seaborn as sns
dt=sns.load_dataset('tips')
#Bar plot with hue parameter
sns.barplot(x='day',y='total_bill',data=dt,hue='sex',palette='Set1')
#Set labels and title
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Sex')
```
![image](https://github.com/user-attachments/assets/3785e5ab-7a86-4f24-a686-f4d4d722d630)

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/03a16ee4-533f-4a57-a466-520e2b8c47fb)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/7f28cf32-2e33-4862-9251-36eec09b39e6)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/690e7a2c-0a19-4941-ae9e-4c81d53d7a92)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/23534ea2-5306-4932-88bf-7795d56ff0f0)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/07797dad-2332-43ab-a598-5e6de8e96e45)

```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/947c3dc3-8f6f-445d-bb87-3cd6641da0d6)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/01e1b4a7-c184-413f-ba98-9dd8843d24cd)

```
import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks
```
![image](https://github.com/user-attachments/assets/7fcedca3-becb-46b1-ba19-6f5d9e45bf71)

```
sns.histplot(data=marks,bins=10,kde=True,stat='count',cumulative=False,multiple='stack',element='bars',palette='Set1',shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Marks')
```
![image](https://github.com/user-attachments/assets/adc8aac7-6a15-42c4-a60e-2c90ab5fe492)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/11195da3-0b42-4fc7-b5dd-4877069f7f03)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/b50791ff-442b-4486-b962-9a4a60552b75)

```
sns.boxplot(x='Pclass',y='Age',data=df,palette='rainbow')
plt.title("Age by Passenger Class,Titanic")
```
![image](https://github.com/user-attachments/assets/1d7429f0-2f8b-45f9-9bdf-10f0be2af295)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
palette="Set3", inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/d3611476-311b-472b-baa7-1ac8247d9c92)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x ='day', y ='tip', data = tip)
```
![image](https://github.com/user-attachments/assets/cdb3a4c6-f8d6-498a-b76e-c96df26783e1)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![image](https://github.com/user-attachments/assets/cfd38056-6d82-4e75-be76-35853703c70a)

```
import seaborn as sns
# use to set style of background of plot
sns.set(style="whitegrid")
# loading data-set
tips = sns.load_dataset("tips")
sns.violinplot(x="tip", y="day", data=tip)
```
![image](https://github.com/user-attachments/assets/626d1d38-fbbc-4b83-a450-c89d0609804b)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/1b768216-c795-47ec-85c2-dd69b6cff387)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/f3a9ffdc-0e54-4edf-b54c-125c25a7fa38)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/a4f2b7c0-332c-4592-9cae-395eb21a61a0)

```
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd  # Import the pandas library
import seaborn as sns
# use pd.read_csv to call the function from the pandas library
mart = pd.read_csv("/content/sample_data/supermarket.csv")
mart
```
![image](https://github.com/user-attachments/assets/f0374df4-dab4-4630-bf57-e89e52e71d6a)

```
mart=mart[['Gender','Payment','Unit price','Quantity','Total','gross income']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/a5d21bf5-079e-40be-9a58-ad7948b649be)

```
sns.kdeplot(data=mart,x='Total')
```
![image](https://github.com/user-attachments/assets/04a77f1c-9740-4952-9fd0-2aa573b7ee4c)

```
sns.kdeplot(data=mart,x='Unit price')
```
![image](https://github.com/user-attachments/assets/d9390365-2426-4989-9d08-080771bb6966)

```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/350eca22-b321-4038-91b2-eba57eeb9edf)

```
sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack')
```
![image](https://github.com/user-attachments/assets/d809146a-1307-4e8c-95d4-868e3d9dfda8)

```
sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack',linewidth=5,palette='Dark2',alpha=0.5)
```
![image](https://github.com/user-attachments/assets/abe9fd16-f28f-4f8f-ab72-c8635ec204fc)

```
sns.kdeplot(data=mart,x='Unit price',y='gross income')
```
![image](https://github.com/user-attachments/assets/e11ba6c3-c423-4cf2-8b7b-799ee695747a)

```
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted")
print(data)
```
![image](https://github.com/user-attachments/assets/3dc7b232-cc6e-4e4b-af39-b12591983c1c)

```
hms=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/cd18f503-8d11-4580-8215-b50772496af2)

# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
