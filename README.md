#EX.NO:1

NAME: NIJANTH K

REG NO: 212224230186

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
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
<img width="1914" height="1137" alt="543188845-0a82c51c-59b9-41d5-bf5a-abfd7b53e0dd" src="https://github.com/user-attachments/assets/d07b3ab2-833e-4fa1-af53-524101cbfc9c" />

```
df.head()
```

<img width="1919" height="1141" alt="543188990-bbdd18d3-de4f-4686-a0d0-880c57668c71" src="https://github.com/user-attachments/assets/055f2b6f-9b37-4528-b7da-cb4456d0deb9" />

```
df.tail()
```

```
df.info()
```

<img width="1904" height="1133" alt="543189757-a9d39420-1ed2-4b08-8cb8-df78cf9518aa" src="https://github.com/user-attachments/assets/f7703df7-55cb-4858-8261-c0e08ade2a95" />

```
df.isnull().sum()
```

<img width="1918" height="1141" alt="543190109-93aae9eb-6860-4d38-809d-18dd31110975" src="https://github.com/user-attachments/assets/e3d7039a-d14e-4bd3-af77-74c21a70e557" />
```
df.isnull().any()
```

<img width="1918" height="1144" alt="543190858-3301a572-9154-41aa-91ae-978737d1aea8" src="https://github.com/user-attachments/assets/4dcbc3c9-347d-46e9-9268-14e94aa36f6e" />

```
df.dropna()
```



```
df.fillna(0)
```

<img width="1915" height="1110" alt="543191776-27ad0b6d-b412-4ee7-9dc7-7353c2664fc3" src="https://github.com/user-attachments/assets/da45c23a-c330-43fe-8804-bc1dc2fac4fe" />

```

df.fillna(method='ffill')
```

<img width="1908" height="1127" alt="543191920-6b24cf0b-f6c9-4a71-a245-713d6507b97f" src="https://github.com/user-attachments/assets/cb2e71c4-85c0-49c2-b18c-8a79e943c751" />

```
df.fillna({'GENDER':'MALE','NAME':'SRI'})
```

<img width="1837" height="1068" alt="543192474-17f4cd96-1526-447a-87af-935b39c95b7e" src="https://github.com/user-attachments/assets/fa5d954b-cadb-42a8-8926-88c97ec82585" />
```
ir=pd.read_csv("/content/iris.csv")
ir
```

![543193409-1d660f6b-560e-4818-92b0-22cd15fda715](https://github.com/user-attachments/assets/207be266-26c7-4bec-ad41-cc3da5c6d1be)
```
ir.describe()

```

![543194608-d0579466-3ff4-4750-b0e0-99e4b4edc8fe](https://github.com/user-attachments/assets/33192d28-6d3e-4913-8fb5-7ac50a548b33)

```

import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

![543195010-9ffcebc3-2384-4919-927d-14c2bd5b1793](https://github.com/user-attachments/assets/a579ca09-4c45-4f55-8a30-d1f719294078)
```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```


![543195232-3b9a5ce1-1727-4b22-92f3-f341b72ecba3](https://github.com/user-attachments/assets/6fb8c3f3-de20-4f9d-9be9-425e46cfa40e)

```
ran=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```

![543196742-baed2042-9696-46bc-93b1-93fc0d47725d](https://github.com/user-attachments/assets/30f2c0e4-6a74-4cba-a61e-04ac97e8776f)

```
sns.boxplot(x='sepal_width',data=ran)
```


<img width="1600" height="950" alt="543197166-46fb024c-32f6-43a5-bc37-dda8d7e7313e" src="https://github.com/user-attachments/assets/35c1645f-e26e-4b35-aa56-08521f11fe0f" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['petal_length']))
z
```

<img width="1600" height="950" alt="543197387-2ce58cf0-65c3-4030-8b96-882f1fb1285b" src="https://github.com/user-attachments/assets/8f88621c-9e8d-4f33-b474-0e8b06fcf02f" />

```
ir1=ir[z<3]
ir1
```


<img width="1600" height="950" alt="543197653-501e3c69-fd79-4784-ae05-ace1a85e3467" src="https://github.com/user-attachments/assets/de134de2-a0d8-4501-9bcf-ea560240eec6" />

# Result

Thus the given data successfully performed data cleaning and saved the cleaned data to a file

```
      <<include your Result here>>
```
