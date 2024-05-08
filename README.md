# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

~~~
1.Import pandas and matplot libraries.
2.import Kmeans algorithm to solve customer segmentation.
3.Using the for loop cluster the given data
4.Predict the output and plot data graphs.
5.Display the output

~~~

## Program:

Program to implement the K Means Clustering for Customer Segmentation.
Developed by:kathirvel.A 
RegisterNumber: 212221230047 

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Dataset-20230524.zip")
data

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```



## Output:




![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/0e3e45f6-1758-46a2-af2b-d2c48be66d62)




![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/2965432b-7088-4628-9908-79b5b3551848)







![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/d96a7b66-18c8-456e-98dc-ca5d44aefeca)







![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/81361826-f3a5-4d3c-bc72-64e8c5c23075)





![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/12739294-8e4a-49fc-b53b-3696958f0889)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
