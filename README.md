# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers



```
# Developed By: KRISHNA PRASAD.S
# Register Number: 212223230108
```



# Coding and Output



## DATA CLEANING

<table>
  <tr>
    <td width=50%>


  ## CODING

  </td>
  <td>
              
## OUTPUT

</td>
</tr>
<tr>
    <td width=50%>


```
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
```
  </td>
  <td>
              

![Screenshot 2024-08-20 191018](https://github.com/user-attachments/assets/0f993a41-db77-40a8-8ef8-dcbb670935d9)


</td>
</tr>

<tr>
    <td width=50%>


```
df.isnull().sum()
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 191813.png>)

</td>
</tr>

<tr>
    <td width=50%>


```
df.isnull().any()
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 191945.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df.dropna()
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 192053.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df.fillna(0)
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 192400.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df.fillna(method = 'ffill')
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 192510.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df.fillna(method = 'bfill')
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 192625.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df_dropped = df.dropna()
df_dropped
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 192716.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df.fillna({'GENDER':'MALE','NAME':'SRI''ADDRESS'
:'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,
'TOTAL':305,'AVG':89.999999})
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 192806.png>)
</td>
</tr>


</table>




## IQR(Inter Quartile Range)

<table>
  <tr>
    <td width=50%>


  ## CODING

  </td>
  <td>
              
## OUTPUT

</td>
</tr>

<tr>
    <td width=50%>


```
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 193316.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
ir.describe()
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 193456.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 193808.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 193915.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|
(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194045.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|
(ir.sepal_width>(c3+1.5*iq)))]
delid

```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194136.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
sns.boxplot(x='sepal_width',data=delid)

```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194221.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset

```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194402.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr

```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194521.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
low = q1 - 1.5*iqr
low
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194615.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
high = q3 + 1.5*iqr
high
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194652.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194739.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
z = np.abs(stats.zscore(df['height']))
z
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194828.png>)
</td>
</tr>

<tr>
    <td width=50%>


```
df1 = df[z<3]
df1
```
  </td>
  <td>
              

![alt text](<Screenshot 2024-08-20 194912.png>)
</td>
</tr>


</table>

# RESULT:
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
