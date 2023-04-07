# Workshop-Multivariate-analysis

# Aim 
   
   To perform multivarient analysis on the given data set.
   
# Algorithm

   1.Clean the data

   2.Remove outliers

   3.Apply the skew function and Kurtosis

   4.Apply Bivariate analysis on numerical and categorical

   5.Apply Multivariate analysis. 
   
# Program
  
   Develpoed by:Kathirvelan.K
   
   Register number:212221220026
   
Bivariate analysis

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_excel("/content/FlightInformation (1).xlsx")
df

df.info()

df.isnull().sum()

df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()

df.shape

df.kurtosis()

df.skew()

sns.boxplot(x=df['Price'],y=df['Dep_Time'],data=df)

sns.scatterplot(x=df["Price"],y=df["Source"],data=df)

sns.displot(df,x="Airline",hue="Destination")

sns.barplot(x=df['Price'],y=df['Source'],data=df)

```

Multivariate analysis

```
plt.figure(figsize=(17,7))
sns.scatterplot(x=df['Price'], y=df['Source'],hue=df['Source'])

states=df.loc[:,["Dep_Time","Price"]]
states=states.groupby(by=["Dep_Time"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)


states=df.loc[:,["Airline","Price"]]
states=states.groupby(by=["Airline"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Airline")
plt.ylabel=("Price")
plt.show()

df.corr(method='pearson')

sns.heatmap(df.corr(),annot=False)

```

# Output

Bivariate analysis

Dataset

![]()

Info

![]()

Null values

![]()

After cleaning

![]()

Shape

![]()

Skew

![]()

Kurtosis

![]()

Scatterplot for numerical and numerical 

![]()

Boxplot for numerical and catagorical 

![]()

Displot

![]()

Barplot

![]()

Multivariate analysis

Price and Source

![]()

Price and Dep_Time

![]()

Price and Airline

![]()

Corr()

![]()

Heatmap

![]()

# Result

  Thus the Bivariate and Multivariate analysis is observerd for the given data set.






