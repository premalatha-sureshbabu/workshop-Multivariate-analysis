# workshop-Multivariate-analysis

# Aim:
To Perform Bivariate/Multivariate Analysis

# Algorithm:
1.Read the given data 2.Get information from the data 3.Perform the Bivariate/Multivariate Analysis
2.Save the clean data to File

# CODE 
NAME:S.Prema Latha
REG.NO:212222230112

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("FlightInformation.csv")
df
df.head()
df.info()
df.isnull().sum()
df['Route'] = df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops'] = df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
plt.figure(figsize=(8,5))
plt.xticks(rotation = 80)
sns.barplot(df["Airline"],df["Price"],hue=df["Total_Stops"])
states=df.loc[:,["Source","Price"]]
states=states.groupby(by=["Source"]).sum().sort_values(by="Price")
plt.figure(figsize=(8,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SOURCE")
plt.ylabel=("PRICE")
plt.show()
plt.figure(figsize=(5,7))
sns.scatterplot(df['Source'], df['Price'], hue=df['Destination'])
plt.xticks(rotation = 90)
df_count = df.groupby(by=["Source"]).count()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette("Set2")
plt.pie(df_count["Price"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.title("Source")
plt.show()
df['Airline'].value_counts()
df['Duration'].value_counts()
df_segment = df.groupby(by=["Total_Stops"]).count()
labels = []
for i in df_segment.index:
    labels.append(i)

plt.figure(figsize=(6,6))
colors = sns.color_palette('pastel')
pie = plt.pie(df_segment["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Total Stops")
plt.legend(pie[0], labels, loc="upper right")
plt.show()
df_region = df.groupby(by=["Destination"]).count()
labels = []
for i in df_region.index:
    labels.append(i)
    
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
pie = plt.pie(df_region["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Destination")
plt.legend(pie[0], labels, loc="upper right")
plt.show()
```

# OUTPUT

![11 1](https://user-images.githubusercontent.com/120620842/229035660-2776439c-8bd6-414a-9a3e-769ac63ca45a.png)

![12](https://user-images.githubusercontent.com/120620842/229035793-00d45ecd-7dfb-43f5-a8f3-15823d3d2af0.png)

![13](https://user-images.githubusercontent.com/120620842/229035829-a54b6ee2-09e7-47be-ae96-5ff2eea3f783.png)

![14](https://user-images.githubusercontent.com/120620842/229035916-806a29fe-4f2f-4959-bfbc-71f424e20ef8.png)

![15](https://user-images.githubusercontent.com/120620842/229035950-79d2db58-fd41-43d0-9c9d-9e2acf8197a3.png)

![16](https://user-images.githubusercontent.com/120620842/229036076-1bab2399-d461-4306-8f45-392798fad3b9.png)

![Screenshot 2023-03-31 113446](https://user-images.githubusercontent.com/120620842/229036710-2bf95252-7976-4cff-9799-b3b30996c6e6.png)


![18](https://user-images.githubusercontent.com/120620842/229036179-8d171157-e393-4e3e-a3de-04e82a409e36.png)

![19](https://user-images.githubusercontent.com/120620842/229036231-3ad768ee-2743-4b40-bccd-9c56e00ec2d4.png)

![20](https://user-images.githubusercontent.com/120620842/229036272-83335f23-7f66-42dc-a5b7-630a3da9f069.png)

![21](https://user-images.githubusercontent.com/120620842/229036310-350b2215-e966-4d8a-ae6f-6ff607304b0f.png)

![22](https://user-images.githubusercontent.com/120620842/229036349-bfaffa84-d3df-47e7-bb49-a5c7bd01ebec.png)

![23](https://user-images.githubusercontent.com/120620842/229036380-a1f3b5f0-7444-49e9-a6c1-08343f8075b8.png)

![24](https://user-images.githubusercontent.com/120620842/229036400-10fd5771-2b9a-44a9-8303-df27de714afe.png)

![25](https://user-images.githubusercontent.com/120620842/229036430-9b1338ee-3663-4399-afd9-fe2f532bbd34.png)

# Result :
Thus we applied Bivariate/Multivariate Analysis Successfully
