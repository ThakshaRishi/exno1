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
```
df['GENDER'].value_counts()
```

# Output

```
df.TOTAL.fillna(mn,inplace=True)
df.M4.fillna(0)
```

# Output

```
min=df.M4.min()
min
```

# Output

```
df.M4.fillna(min,inplace=True)
df
```

# Output

```
df.isnull()
```

# Output


```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

# Output

```
sns.boxplot(data=af)
```

# Output

```
sns.scatterplot(data=af)
```

# Output

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```

# Output

```
low=q1-1.5*iqr
low
```

# Output

```
high=q3+1.5*iqr
high
```

# Output

```
af=af[((af>=low)&(af<=high))]
af
```

# Output

```
af.dropna()
```

# Output

```
sns.boxplot(data=af)
```

# Output

```
data=[1,12,15,18,21,24,27,20,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,158]
df=pd.DataFrame(data)
df
```

# Output

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```


# Result
 Thus, we have read the given data and performed data cleaning and saved the cleaned data to a file successfully.
