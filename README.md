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
Developed by: MITHUN G
RegisterNumber:  212223080030
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
data

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km=KMeans(n_clusters = 5)
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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments   ")
```

## Output:

![image](https://github.com/user-attachments/assets/2b1212c1-6d3b-4a28-b235-20cb0fee2109)


data.head()


![image](https://github.com/user-attachments/assets/249d963c-d436-4d15-a98b-ba5f2be0295c)

data.info()


![image](https://github.com/user-attachments/assets/758264d6-2774-494c-b53c-4e2f5c95483c)

data.isnull().sum()


![image](https://github.com/user-attachments/assets/3675be4f-50fe-4d43-bf43-a071b5f115a4)


![image](https://github.com/user-attachments/assets/22566788-76ad-46c3-b4ff-f4f7e4626389)


Elbow method graph


![image](https://github.com/user-attachments/assets/c03a9a34-e216-4c58-9615-52ddfe08be7e)

Kmeans cluster


![image](https://github.com/user-attachments/assets/436a106f-a9df-44a6-bff9-239a6eef92ac)

y_pred


![image](https://github.com/user-attachments/assets/c896e552-9280-4932-8a3b-a98b1f6dd228)


Customers Segments Graph


![image](https://github.com/user-attachments/assets/0db39035-adb9-4160-a106-3db68afdef86)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
