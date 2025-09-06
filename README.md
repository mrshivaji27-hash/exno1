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

# Coding
import numpy as np
import pandas as pd
data=pd.read_csv("/SAMPLEIDS (1).csv")
data
# Output
<img width="1201" height="842" alt="image" src="https://github.com/user-attachments/assets/d6025ed7-7051-4d01-a68c-5f094d4d7854" />

```
data.head()

```
# Output:
<img width="1089" height="327" alt="image" src="https://github.com/user-attachments/assets/6ce33e2c-7ff2-4925-808d-31e02acb176a" />

```
data.tail()

```
# Output:

<img width="1015" height="300" alt="image" src="https://github.com/user-attachments/assets/30eb2df3-95b6-453d-8659-da50b058d04c" />

```
data.isnull()

```
# Output:

<img width="840" height="842" alt="image" src="https://github.com/user-attachments/assets/c367d423-f23f-422a-a18b-db4f4852c441" />

```
data.notnull()

```
# Output:
<img width="823" height="847" alt="image" src="https://github.com/user-attachments/assets/41205ff5-8c64-411b-9179-6983cc746241" />

```
data.isnull().sum()

```
# Output:

<img width="242" height="567" alt="image" src="https://github.com/user-attachments/assets/40f3cd67-57cc-42c1-b19c-fe02de657fba" />

```
data.isnull().any()
```
# Output:

<img width="217" height="584" alt="image" src="https://github.com/user-attachments/assets/1e5ab124-bb76-4966-b42f-3fbd37b31d15" />

```
data.dropna(axis=0)

```
# Output:
<img width="1017" height="615" alt="image" src="https://github.com/user-attachments/assets/c6dce8a3-a319-44b5-a09b-be3db1d6af19" />

```
data.fillna(7)

```
# Output:

<img width="1020" height="830" alt="image" src="https://github.com/user-attachments/assets/4fe5781d-7e6a-4b96-b992-1a9b0cb9c864" />

```
data.dropna(axis=1)

```

# Output:
<img width="292" height="848" alt="image" src="https://github.com/user-attachments/assets/22d08ef3-8da2-47be-ab26-e8f52117e1bf" />

```
data.ffill()

```
# Output:

<img width="1028" height="858" alt="image" src="https://github.com/user-attachments/assets/140eb631-384a-4f5f-b3d6-4b0c918e9c5a" />

```
data.bfill()

```
# Output:

<img width="1021" height="842" alt="image" src="https://github.com/user-attachments/assets/b872ac1d-60ec-40a9-a78e-d02e285c0534" />

```
data.fillna(method="ffill")

```
# Output:

<img width="1684" height="844" alt="image" src="https://github.com/user-attachments/assets/d0b82145-61c7-437d-9678-688fc1aa557b" />

```
data.fillna({'GENTER':'MALE','NAME':'shivaji'})
```
# Output:
<img width="1044" height="831" alt="image" src="https://github.com/user-attachments/assets/2d9bb121-f83a-4677-ac8a-a2d240e5c483" />

```
ir=pd.read_csv("/iris (1).csv")
ir

```
# Output:

<img width="669" height="574" alt="image" src="https://github.com/user-attachments/assets/a262c84e-6932-415e-88d5-65f252061701" />

```
ir.describe()

```
# Output:
<img width="611" height="427" alt="image" src="https://github.com/user-attachments/assets/05cd4a49-4cea-49e4-84d3-74f1d053892d" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)

```

# Output:
<img width="704" height="662" alt="image" src="https://github.com/user-attachments/assets/9727bd54-42f6-4960-bcb0-1ffb4732db31" />

```
 Q1=ir.sepal_width.quantile(0.25)
 Q3=ir.sepal_width.quantile(0.75)
 iqr=Q3-Q1
 print(iqr)

```
# Output:
<img width="690" height="309" alt="image" src="https://github.com/user-attachments/assets/44141fd8-f7d4-45b8-9f4f-a9cc4adc6355" />

```
delid=ir[~((ir.sepal_width>(Q1-1.5*iqr))&(ir.sepal_width<(Q3+1.5*iqr)))]
delid

```
# Output:
<img width="709" height="289" alt="image" src="https://github.com/user-attachments/assets/7609e282-ed10-4cb1-b208-0f9367577763" />

```
sns.boxplot(x='sepal_width',data=delid)

```
# Output:
<img width="732" height="621" alt="image" src="https://github.com/user-attachments/assets/6bf23808-2d0d-446c-aaaa-52cff64a1425" />

```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats

z = np.abs(stats.zscoreir['sepal_widt']))
z

```
# Output:
<img width="766" height="743" alt="image" src="https://github.com/user-attachments/assets/de8461da-0671-428f-a04c-7467d926431b" />


# Result
          Thus the given programs were run successfully.
