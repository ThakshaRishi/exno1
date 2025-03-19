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

![image](https://github.com/user-attachments/assets/157c9451-912a-4653-bfc3-f4e592be267f)

```
df.info()
```

# Output

![image](https://github.com/user-attachments/assets/d698be08-0eeb-4e3b-a339-47b3733530a9)

```
df.describe()
```

# Output

![image](https://github.com/user-attachments/assets/f2215ca3-d85a-42cd-a5bd-b5153cf57619)

```
df.shape
```

# Output

![image](https://github.com/user-attachments/assets/dcd29ddf-8d04-452a-ab79-d44be5c3f09c)


```
df.isnull().sum()
```


# Output

![image](https://github.com/user-attachments/assets/693f398c-ac69-45d3-b92e-8aa66efed65f)

```
df.nunique()
```

# Output

![image](https://github.com/user-attachments/assets/9f01c03a-e23d-45a7-8bee-545626976864)


```
mn=df.TOTAL.mean()
mn
```

# Output

![image](https://github.com/user-attachments/assets/86088890-1885-44c2-84e6-94b2ff53b9b0)

```
df['GENDER'].value_counts()
```

# Output

![image](https://github.com/user-attachments/assets/5bd009b9-5cba-4c73-9356-37700429779f)

```
df.TOTAL.fillna(mn,inplace=True)
df.M4.fillna(0)
```

# Output

![image](https://github.com/user-attachments/assets/1331a09e-608f-4bc0-abb8-ffb647a29c5d)

```
min=df.M4.min()
min
```

# Output
![image](https://github.com/user-attachments/assets/736e4a06-509e-4f3b-8331-87cba715a706)

```
df.M4.fillna(min,inplace=True)
df
```

# Output

![image](https://github.com/user-attachments/assets/0c201304-ba5a-4dc8-a8d2-1abd3a2d3d90)


```
df.isnull()
```

# Output

![image](https://github.com/user-attachments/assets/e4b29ed5-51b1-4b8c-b323-70ab5b48c564)


```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

# Output

![image](https://github.com/user-attachments/assets/2714632c-84d4-46b1-8be9-7075c5e2bdae)

```
sns.boxplot(data=af)
```

# Output

![image](https://github.com/user-attachments/assets/78ec4cda-1aca-490a-baa1-2a2e67ce8e17)

```
sns.scatterplot(data=af)
```

# Output

![image](https://github.com/user-attachments/assets/b7d144d7-8591-46d5-a582-93eb511020a7)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```

# Output

![image](https://github.com/user-attachments/assets/1252fa9f-f6a8-4fa9-b1af-6107947ef145)

```
low=q1-1.5*iqr
low
```

# Output

![image](https://github.com/user-attachments/assets/e9937ee2-1905-4fcc-8257-30349d7d24ab)

```
high=q3+1.5*iqr
high
```

# Output

![image](https://github.com/user-attachments/assets/f94fef2d-3cc0-4f10-8fec-b968f8256694)

```
af=af[((af>=low)&(af<=high))]
af
```

# Output

![image](https://github.com/user-attachments/assets/779c9288-d0d6-401b-9493-f735619b57ac)

```
af.dropna()
```

# Output

![image](https://github.com/user-attachments/assets/9d8a4906-f79a-4694-a882-281a2bfdee76)

```
sns.boxplot(data=af)
```

# Output

![image](https://github.com/user-attachments/assets/9be7913f-900e-4341-95c5-a9062b5bd66e)

```
data=[1,12,15,18,21,24,27,20,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,158]
df=pd.DataFrame(data)
df
```

# Output

![image](https://github.com/user-attachments/assets/64e22172-c7a9-41d6-9ff7-571c14ee0e7f)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
# Output

![image](https://github.com/user-attachments/assets/fe5f8dbb-f92e-4947-a0da-3427c31926c0)


# Result
 Thus, we have read the given data and performed data cleaning and saved the cleaned data to a file successfully.
