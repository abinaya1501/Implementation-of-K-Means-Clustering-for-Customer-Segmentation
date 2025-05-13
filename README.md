# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program

## Program:

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: ABINAYA A

RegisterNumber:212224230004

```python

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```


## Output:
![Image-1](https://github.com/user-attachments/assets/1267295d-3c52-40b9-a04f-7a3695ca5da5)

![Image-2](https://github.com/user-attachments/assets/5c563eaa-861a-47af-9567-b0313a197220)

![Image-3](https://github.com/user-attachments/assets/329d92eb-caab-44de-84be-45bd3ac1ebc8)

![Image-4](https://github.com/user-attachments/assets/34cd379a-df77-450e-85d1-78aaddbaf0f9)

![Image-5](https://github.com/user-attachments/assets/8dcff655-2a25-45dc-8ecf-789ca45d248d)

![Image-6](https://github.com/user-attachments/assets/014556e6-5bf0-429a-9945-6d8970708430)

![Image-7](https://github.com/user-attachments/assets/eb409435-1cc3-45c0-af33-1d4d17993020)

![Image-8](https://github.com/user-attachments/assets/538f0561-db96-4468-bdfd-0cdcf36853ca)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
