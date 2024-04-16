# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.
2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3.Import KMeans and use for loop to cluster the data.
4.Predict the cluster and plot data graphs.
5.Print the output and end the program. 


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: santhosh kumar B
RegisterNumber: 212223230193 
*/
```
import numpy as np
import pandas as pd

import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
kmeans=KMeans(n_clusters = i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-
100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-
100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-
100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-
100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-
100)"],c="magenta",label="cluster4")

plt.legend()
plt.title("Customer Segmets")

## Output:
![K Means Clustering for Customer Segmentation](sam.png)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/572a6946-42aa-4ea5-9d56-293f830bd9f8)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/477a07f0-b952-44c0-b441-03ec1989be54)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/3b120e9d-3c87-4338-b3a2-7e0e73336c6c)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/30e6d09d-d005-4524-89a1-6e71391fdb81)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/3c59d4a5-c1a6-4bff-b66d-3cc6df25183c)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/4ec0c6c5-bd19-421f-ad1e-8e73735e5f0f)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/852d2811-c474-40a8-94bd-da0792a49b00)

![image](https://github.com/Santhoshstudent/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145446853/16316f52-d582-43a5-92ee-8cc1b83a02fa)










## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
