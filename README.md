# EXPLORE-BUISNESS-ANALYTICS
# imported all packages
import pandas as pd
import numpy as np  
import matplotlib.pyplot as plt  
import plotly
import seaborn as sns
%matplotlib inline
from google.colab import files 
uploaded = files.upload()
data1=pd.read_csv('/content/SampleSuperstore.csv')
print('data imported successfully')
data1
data1.iloc[10]
data1.describe()
# data mean
data1.mean()
data1.plot()
data1.hist(figsize=(12,17),bins=30)
sns.heatmap(data1.corr(),annot=True)
data1.corr().plot.bar()
sns.countplot(x='Category',data=data1).set_title("most sold product")
sns.countplot(x='Sub-Category',data=data1).set_title("most sold Sub-Category")
plt.xticks(rotation=270)
plt.scatter(x=data1['Sales'],y=data1['Profit'])
plt.xlabel('Total Sales')
plt.ylabel("Profit")
plt.show()

sns.countplot(x='Region',data=data1,palette='hls')
sns.countplot(x='Region',hue='Category',data=data1,palette='dark')
