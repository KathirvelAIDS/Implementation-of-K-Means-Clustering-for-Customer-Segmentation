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


DATA.HEAD():

![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/8a60f9cd-a5ca-43d9-aa27-5e8002bcfabd)



DATA.info():


![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/99555b1e-f1da-489f-8ade-3290c0bb0e18)




NULL VALUES:


![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/40ffa4dc-a7ba-4cd9-ad77-833b22885dc4)



ELBOW GRAPH:



![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/fd156d40-431c-42ce-872e-075698f48dd9)




CLUSTER FORMATION:



![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/c7b31969-c519-46d7-9264-4aa85bf9fea6)




PREDICICTED VALUE:


![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/11d8c3ee-9f34-49f6-9db5-2a941a7c137b)




FINAL GRAPH(D/O):




![image](https://github.com/KathirvelAIDS/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94911373/4fde4b6a-c249-4539-8b45-065190526922)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
