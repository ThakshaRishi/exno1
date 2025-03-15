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

# Coding and Output

```
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
```
# Output
![image](https://github.com/user-attachments/assets/36307fbd-d4b0-4dac-aaf6-1467310e7cf4)

```
df.head(5)
```

# Output
![image](https://github.com/user-attachments/assets/c2a7cfad-f829-468d-934e-812d04306c29)

```
df.tail(5)
```
# Output

```
df.info()
```

# Output

```
df.describe()
```

# Output


```
df.shape()
```

# Output


```
df.isnull().sum()
```


# Output

```
df.nunique()
```

# Output


```
mn=df.TOTAL.mean()
mn
```

# Output

# Result
          <<include your Result here>>
