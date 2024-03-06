### 1- Install version 1.1.4
`pip install pandas==1.1.4`

### 2- Import
`import pandas as pd`

### 3- Define data frame (Table with 2 rows and 3 columns)
`df=pd.DataFrame([100,101,102], [1,2])` <br>
*to have indexed data frame:* <br>
`df=pd.DataFrame({'id':[100,101,102], 'color':['red','blue','green']}, index=['a','b','c'])`

### 4- Read csv - xlsx file
`df=pd.read_csv('file-name.csv)`*to read just 10 rows:* `df=pd.read_csv('file_name.csv', nrows=10)` <br>
*to conver some values to Null:* `missing_val = ["na", "n/a", "-"]` `df=pd.read_csv('file-name.csv, na_values=missing_val)`
`df=pd.read_excel('file-name.xlsx)` *to read just 10 rows:* `df=pd.read_excel('file_name.xlsx', nrows=10)` <br>
`df=pd.read_pickle('file_name.pkl')`

### 5- Save csv - xlsx file
`df.to_csv('file-name.csv, index=False)` <br>
`df.to_excel('file-name.xlsx, index=False)` <br>
`df.to_pickle('file_name.pkl')`

### 6- Depict top and last 10 rows (default number is 5)
`df.head()` <br>
`df.head(10)` *or* `df[:10]` <br>
`df.tail()` <br>
`df.tail(10)`

### 7- Depict column namely "Age" and 2nd row of it
`df.Age` *or* `df['Age']`
*indexes are started from 0* `df.['Age'][1]`

### 08- Add New Column namely "id" from index values
`df['id']=df.index`

### 09- Copy whole data of df to temp
`temp=df.copy()` *or* `temp=df` *for selecting columns namely A and B:* `temp=df[['A','B']]`

### 10- Shape or Size
`df.shape`

### 11- Convert data to True and False based on being Not Null
`df.notnull()`

### 12- Depict how many Null values are exist
`df.isnull().sum()` *to depict true and false for bring null:* `df.isnull()`

### 13- Fill Null Values in column "Age" by 2 (for instance)
`df['Age'].fillna(value=2, inplace=True)` *use inplace to make changes applyed - alternatiopn for inplace is:* `df['Age']=df['Age'].fillna(value=2)`

### 14- Remove Null Values in column "Age"
*to remove any row that whole are Null:* `df['Age'].dropna(how='all', inplace=True)` <br>
*to remove any row contain even one Null values:* `df.dropna(how='any', inplace=True)` <br>
*to remove any row contain 5 Not Null values:* `df.dropna(thresh=5, axis=1, inplace=True)` 

### 15- Remove Columns namely "Age" and "Name" and Remove Rows with index=0 and 2
`df.drop(['Age', 'Name'], axis=1, inplace=True)` <br>
`df.drop([0, 2], axis=0, inplace=True)`

### 16- Count how many 2 values are in column "Age"
`df[df.Age==2].count()` <br>
*To count them by multiple conditions:* `df[(df.Age>2) & (df.Age<10)].count()`

### 17- Replace A with another B in Column namely "Name"
`df.Name.replace('A', 'B', inplace=True)` *or* `df.Name=df.Name.replace('A', 'B')`

### 18- Remove "A" from values of Column namely "Name" from right, left and both side of string
*for right:* `df.Name.str.rstrip('A')` <br>
*for left:* `df.Name.str.lstrip('A')` <br>
*for both:* `df.Name.str.strip('A')`

### 19- Remove rows contain a value for strings and greater(or less) than a value for numbers 
`df=df[df.Name.contains('A')==Flase]` *for special signs like \* use \\** <br>
`df=df[df.Age>100]`

### 20- Change strings to Upper or Lower cases
`df.Name.str.upper()` <br>
`df.Name.str.lower()`

### 21- Count group of values
`df.Age.value_counts()`

### 22- Rename Column namely 'Age' to 'During'
`df.rename(columns={'Age':'During'}, inplace=True)` *to rename whole Columns:* `df.columns=['a','b',...]`

### 23- Get columns name and data type
`df.columns` *to show them in list:* `df.columns.tolist()` <br>
`df.dtypes` *or for "Age" column:* `df.Age.dtypes` *'str' is shown as object*

### 24- Conver data type e.g. string dtype of "Age" to float
`df.Age.astype(float)`

### 25- Categorize column "Age" and get codes ang categories' name
`df.Age=df.Age.astype('category')` <br>
`df.Age.cat.codes` *-1 is shown for NaN values*<br>
`df.Age.cat.categories`

### 26- Sort data by column namely "Age"
`df.sort_values(by="Age", ascending=True, inplace=True)` <br>
*for one column:* `df.Age.sort_values()`

### 27- Depict memory usage of each columns
`df.memory_usage(deep=True)`

### 28- Depict a general details of columns e.g. count, mean, std, min, etc.
`df.describe()` *for bit shorter info:* `df.info()`

### 29- Depict count, mean, std, min, etc of data or each columns
`df.max()` *or* `df.Age.max()` *ro get index of them add arg to them:* `df.argmax()` <br>
`df.Age.value_counts(dropna=False)` *if do not want to count null values, change it to True (default is True) <br>
*for depicting in percantage mode (normalized), add* `normalize=True` <br>
*list of indexes* `df.Age.value_counts().index` <br>
*list of values* `df.Age.value_counts().values` <br>
*unique of values* `df.Age.uniques()`

### 30- Dammy variables
*to change unique values of column Age:* `df.Age.map({1:'One', 2:'Two'})` *or* `df.Age={1:'One', 2:'Two'}` <br>
*to make a word bag specially for categories:* `df.get_dummies(df.Age)`

### 31- Choose the column Age as index of data frame
`df.set_index("Age", inplace=True)` <br>
*to remove the name of index column or assign a name:* `df.inedx.name="AgeIndex"` `df.index.name=None` <br>
*to reset index values (0~ ...):* `df.reset_index(inplace=True)`

### 32- Access to rows by index of them
`df.iloc[[10, 30]]` *min, max, mean, argmax , etc can be used instead of list* <br>
*to get value of special columns:* <br> 
`df.iloc[[10]]["Age"]` *or* `df.iloc[[10]].Age` *or* `df.loc[10, "Age"]` *or* `df.at[10, "Age"]`

### 33- Filter data frame by column namely Age value
`df[df.Age>10]` *to filter by more than one columns:* `df(df.Age>10) & (df.Name.contains('A'))]` <br>
*to depict just True or False for all of data:* `df.Age>10` <br>
*to check whether they exist in a list or not:* `df.Age.isin([10,20,30])`

### 34- Group data by a column value
`df.groupby("Age")` *to count, mean, min, max, etc:* `df.groupby("Age").count()` *or* `df.groupby("Age").Name.sum()` <br>
*to get more details based by groups:* `df.groupby("Age").Age.agg(["count", "sum", "min", "max"])`

### 35- DataFrame Iteration
```
for index, row in df.iterrows():
  codes...
```

### 36- Depict some rows randomly
`df.sample(n=3, random_state=65)` *if want to have same results in different excution, use random_state* <br>
*to select 5 percent of whole data frame:* `df.sample(frac=0.05)` <br>
*if you want to shuffle whole data:* `df.sample(frac=1)`

### 37- Depict Duplicated values
`df.duplicated()` *or for checking column namely Age:* `df.Age.duplicated()` <br>
*to get number of duplicated values:* `df.Age.duplicated().sum()` <br>
*to remove duplicated values:* `df.drop_duplicates(inplace=True)`

### 38- Functions (keyword: apply)
*to get lenghth of a column in string dtype:* `df['name_lenghth']=df.Name.apply(len)` <br>
*to add 2 to Ages:* `df.Age+=2` *to make it as a function:* <br>
```
def get_element(num):
  return num+2
  
df[temp_age]=df.temp_age.apply(get_element)
```
*if want to change data more than 8 to 1 and less that it to 0:*
```
import numpy as np

df=pd.DataFrame()
df['temp_age']=np.where(df.Age>8 ,1 ,0)
```
*Choose 10 random samples of column Age with values greater than '50' and Name equal to 'Ali':*
```
df1=df[df.Age>1].sample(n=10)
df2=df[df.Name=='Ali'].sample(n=10)

df_all=pd.concat([df1,df2]).sample(frac=1)
```

