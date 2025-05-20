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

Developed by: Mukesh R

RegisterNumber: 212224240098
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
![image](https://github.com/user-attachments/assets/f09f2a6a-8f92-4bd9-9e3e-36457ac761e7)

![image](https://github.com/user-attachments/assets/004294f5-d760-4183-871b-899453d24b39)

![image](https://github.com/user-attachments/assets/442fe482-2df5-4269-8053-731cdb8a5db1)

![image](https://github.com/user-attachments/assets/e5b33096-e992-4873-9567-6a38d23bdec5)

![image](https://github.com/user-attachments/assets/69080fcd-6ef4-4384-88ab-eec4a50791cc)

![image](https://github.com/user-attachments/assets/6d5e03ad-fe1c-48ac-b3b0-c43b0a3e5291)

![image](https://github.com/user-attachments/assets/411ca391-ca94-4a50-b3b0-3a0e42a9e0d2)

![image](https://github.com/user-attachments/assets/1470d078-53f3-489f-bca7-501cb22213e7)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
