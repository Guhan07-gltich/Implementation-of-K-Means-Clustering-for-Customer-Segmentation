# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
step1: Import the necessary packages using import statement.

Step2: Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

Step3: Import KMeans and use for loop to cluster the data.

Step4: Predict the cluster and plot data graphs.

Step5: Print the outputs and end the program.


Program: 

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ETHICVARAN S
RegisterNumber: 212224230072


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r"C:\Users\acer\Downloads\Mall_Customers.csv")
data.head()
```

<img width="1105" height="321" alt="593475226-ede4ac4b-7b4d-48d8-b430-db986ede667f" src="https://github.com/user-attachments/assets/67c16631-fcf7-4758-a32b-0234be6276d1" />

```
data.info()
```

<img width="1037" height="401" alt="593475502-e5585068-c1b8-43a0-9bb1-51af81cc9c81" src="https://github.com/user-attachments/assets/c0c6136c-e189-4314-b014-9782e57069ac" />

```
data.isnull()
```

<img width="1188" height="617" alt="593475565-1718465e-d347-4e39-8f94-675789669d23" src="https://github.com/user-attachments/assets/9510c65c-eae7-4f0e-b699-11d6623ced16" />


```
data.isnull().sum()
```

<img width="722" height="207" alt="593475649-2dcc8306-7f95-47f0-80b6-c39cf08553ad" src="https://github.com/user-attachments/assets/44107639-ad86-4923-a5ac-7a1c178d39a2" />


```
from sklearn.cluster import KMeans
wcss= [] 
for i in range(1,11):
    kmeans=KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```

<img width="1062" height="717" alt="593476045-195d87c4-a0d6-426d-9e91-0d90d83b758c" src="https://github.com/user-attachments/assets/6c8a7f37-d243-494d-8dea-785c7cb9f57e" />


```
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
```

<img width="1257" height="353" alt="593476331-7750bed5-3af9-4430-8baf-43d0e6c4e781" src="https://github.com/user-attachments/assets/5c7a42f2-ae9f-49c1-b1ac-6248c52c8b22" />


```
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="black",label="cluster")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="cyan",label="cluster")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cluster")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="cluster")
plt.legend()
plt.title("Customer Segments")
```

<img width="1191" height="811" alt="593476680-5b64f304-c7e4-4c40-8c5d-ea8002cac717" src="https://github.com/user-attachments/assets/24d81154-22f2-4560-bac8-167b2198a9ee" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
