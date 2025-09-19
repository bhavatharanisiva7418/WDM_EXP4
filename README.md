### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 19-09-2025
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program 1:
```python
import pandas as pd
df=pd.read_csv("/content/clustervisitor.csv")
df.head()
cluster={"young":(df['Age']<=30),"Middle":((df['Age']>30)&(df['Age']<=60)),"Old":(df['Age']>50)}
cluster
count=[]
for  g,c in cluster.items():
  visitors=df[c]
  count.append(len(visitors))
  print(f"visitors in {g} Group")
  print(visitors)
  print(count)
plt.figure(figsize=(8,6))
plt.bar(cluster.keys(),count,color="skyblue")
plt.xlabel("Age Groups")
plt.ylabel("Number of Visitors")
plt.title("VisitorsDistribution Across Age Groups")
```
### Output:
<img width="698" height="663" alt="image" src="https://github.com/user-attachments/assets/e190aa90-a9e5-4cfb-b819-8e829e879a72" />

<img width="1107" height="724" alt="image" src="https://github.com/user-attachments/assets/9ffc21a7-d268-467b-8ada-331e30e1b68c" />

### Program 2:

```python
kmeans=KMeans(n_clusters=3,random_state=42)
df3['cluster']=kmeans.fit_predict(df3)
df3
plt.scatter(df3['Age'],df3["Salary"],c=df3["cluster"])
plt.xlabel("Age")
plt.ylabel("Income in thousand")
plt.show()
```
### Output:

<img width="481" height="676" alt="image" src="https://github.com/user-attachments/assets/c2d87347-bf52-489f-9d8a-73352d166906" />

<img width="754" height="431" alt="image" src="https://github.com/user-attachments/assets/28a06779-e428-4e8d-9f0c-435e055ca60a" />

### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully
