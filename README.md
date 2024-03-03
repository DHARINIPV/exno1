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

### Developed by: Dharini PV
### Register No: 212222240024

# Coding and Output
```python
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/af14e2bd-bcb3-40de-9747-62d2fb7b3089)

```python
df.head()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/3d9e680f-2418-4156-ab67-69d271e78fd8)

```python
df.tail()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/26612e66-4e75-46f8-af0a-606a4452224d)

```python
df.info()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/bd036459-2cfe-4e1f-9bdd-84ae7a8ab81e)

```python
df.describe()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/514b178f-5b8d-450f-96dc-3621443a367f)

```python
df.shape
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/6ee18a93-e418-4cab-9f49-83f043048233)

```python
df.isnull().sum()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/0d41fa4d-15b5-4e13-82c2-0127afda1854)

```python
df.nunique()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/50ead141-01ef-4335-8a95-af038616ac2c)

```python
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/982756cb-fb2c-4e1b-8644-8b6e25368fd8)
```python
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/281a6f09-7410-45a4-8fb4-88589a9d2183)
```python
df.duplicated()
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/2e889626-8b55-42b2-b2f5-371d0751e7b4)
```python
df.drop_duplicates(inplace=True)
df
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/b257561a-8ad5-4ebc-aa65-fba176d82ec3)
```python
df['DOB']
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/5f2fc65c-5cc1-49f5-b5ad-d106d53276d4)

```python
df['DOB']=pd.to_datetime(df['DOB'])
df
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/8563f4a6-1a64-41fa-bc6f-6e7e59a383aa)
```python
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/9402d312-463f-4458-b4e9-c08f60fdead6)
```python
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/DHARINIPV/exno1/assets/119400845/92ad64ec-4748-4112-8301-80c3b6255a41)

### 
# Result
Thus the outliers are detected and removed in the given file and the final data set is saved into the file.
