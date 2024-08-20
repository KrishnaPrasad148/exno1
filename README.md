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
              
#### OUTPUT:
![Screenshot 2024-08-20 191018](https://github.com/user-attachments/assets/0f993a41-db77-40a8-8ef8-dcbb670935d9)


</td>
</tr>
</table>

# RESULT:
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
