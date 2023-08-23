# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE :
## CODE FOR DATA SET:
```
import pandas as pd
import numpy as np
from google.colab import files
upload = files.upload()
df=pd.read_csv('Data_set.csv')
df.isnull().sum()
df.shape
df['show_name'].nunique()
df=df.dropna(subset=['show_name'])
df['aired_on'].value_counts()
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['original_network'].mode()[0])
df['rating']=df['rating'].fillna(df['rating'].mode()[0])
df=df.dropna(subset=['current_overall_rank'])
df['watchers']=df['watchers'].fillna(df['watchers'].median())
df_reset=df.reset_index(drop=True)
df=df.drop(columns=['index','level_0'])
df
```
## CODE FOR LOAN DATA:
```
import pandas as pd
import numpy as np
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('Loan_data.csv')
df.info()
df.head()
df['Gender']=df['Gender'].fillna('Female')
df.head()
df['Dependents']=df['Dependents'].fillna(method='ffill')
df.head()
df['Self_Employed']=df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df.head()
df=df.dropna(subset=['LoanAmount'])
df.head()
df['Loan_Amount_Term']=df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].median())
df.head()
df['Credit_History']=df['Credit_History'].fillna(df['Credit_History'].min())
df.head()
df.info()
```
## OUTPUT:
## OUTPUT FOR DATA SET:
![Screenshot (113)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/40314902-3dd7-4c62-9dc0-741878356802)
![Screenshot (114)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/1d2f2f1a-ed6f-4122-a39e-628c96a13017)
![Screenshot (115)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/18647e51-4950-4039-a9c5-540ba5c0d690)
![Screenshot (116)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/2451f9b8-5639-490d-8b4e-fa81c756189e)

## OUTPUT FOR LOAN DATA:
![Screenshot (117)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/08285bbd-53a4-4280-b7ba-6e422f2d3472)
![Screenshot (118)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/939efcdd-d6ee-4ed2-8bc9-49be63d637b4)
![Screenshot (119)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/4fa51f47-040d-4f09-b17c-9e98d82ce684)
![Screenshot (120)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/b3048d16-0709-42f6-8352-1731b8a38068)
![Screenshot (121)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/2b5dc840-8253-4437-8b28-074bb078ba37)
![Screenshot (122)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/4f8efb2a-ea9c-45fb-b99f-9146c46baf7f)
![Screenshot (123)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/8f65035f-838a-4c80-874b-fb45d6b86c28)
![Screenshot (124)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/03c8326e-b72f-4c8d-b911-4d0af7cdf240)
![Screenshot (125)](https://github.com/gowrisankarponnusamy/ODD2023-Datascience-Ex01/assets/119393123/782a6f39-3d3b-44b0-bf7d-87cb1f4fd255)

