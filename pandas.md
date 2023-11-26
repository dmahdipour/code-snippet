### 1- Install version 1.1.4
`pip install pandas==1.1.4`

### 2- Import
`import pandas as pd`

### 3- Define data frame (Table with 2 rows and 3 columns)
`df=pd.DataFrame([100,101,102], [1,2])`

### 4- Define data frame contain index
`df=pd.DataFrame({'id':[100,101,102], 'color':['red','blue','green']}, index=['a','b','c'])`

### 5- Read csv - xlsx file
`df=pd.read_csv('file-name.csv)`<br>
`df=pd.read_excel('file-name.xlsx)`

### 6- Save csv - xlsx file
`df=pd.to_csv('file-name.csv, index=False)`<br>
`df=pd.to_excel('file-name.xlsx, index=False)`

### 7- Depict top 10 rows (default number is 5)
`df.head()`<br>
`df.head(10)` *or* `df[:10]`

### 8- Depict bottom 10 rows (default number is 5)
`df.tail()`<br>
`df.tail(10)`

### 9- Depict column namely "Age"
`df.Age` *or* `df['Age']`

### 10- Depict 2nd row of column namely "Age"
`df.['Age'][1]`

### 11- Add New Column namely "id" from index values
`df['id']=df.index`

### 12- Copy whole data of df to temp
`temp=df.copy()` *for selecting columns namely A and B:* `temp=df[['A','B']]`

### 13- Shape or Size
`df.shape`

### 14- Convert data to True and False based on being Not Null
`df.notnull()`

### 15- Depict how many Null values are exist
`df.isnull().sum()`

### 16- Count how many 2 values are in column "Age"
`df[df.Age==2].count()`

### 17- Fill Null Values in column "Age" by 2 (for instance)
`df['Age'].fillna(value=2, inplace=True)` *use inplace to make changes applyed - alternatiopn for inplace is:* `df['Age']=df['Age'].fillna(value=2)`

### 18- Remove Null Values in column "Age"
`df['Age'].dropna(how='all', inplace=True)`

### 19- Remove any row contain Null values
`df.dropna(how='any', inplace=True)`

### 20- Remove Column namely "Age"
`df.drop(['Age'], axis=1, inplace=True)`

### 21- Remove Row with index=0
`df.drop(index=0, axis=0, inplace=True)`

### 22- Replace A with another B in Column namely "Name"
`df.Name.replace('A', 'B', inplace=True)` *or* `df.Name=df.Name.replace('A', 'B')`

### 23- Remove "A" from values of Column namely "Name" from right, left and both side of string
*for right:* `df.Name.str.rstrip('A')`<br>
*for left:* `df.Name.str.lstrip('A')`<br>
*for both:* `df.Name.str.strip('A')`

### 24- Change strings to Upper or Lower cases
`df.Name.str.upper()`<br>
`df.Name.str.lower()`

### 25- Count group of values
`df.Age.value_counts()`

### 26- Rename Column namely 'Age' to 'During'
`df.rename(columns={'Age':'During'}, inplace=True)` *to rename whole Columns:* `df.columns=['a','b',...]`

### 27- Get columns name and data type
`df.columns` *to show them in list:* `df.columns.tolist()`<br>
`df.dtypes` *or for "Age" column:* `df.Age.dtypes` *'str' is shown as object*

### 28- Conver data type e.g. string dtype of "Age" to float
`df.Age.astype(float)`

### 29- Categorize column "Age" and get codes ang categories' name
`df.Age=df.Age.astype('category')`<br>
`df.Age.cat.codes` *-1 is shown for NaN values*<br>
`df.Age.cat.categories`

### 30- Sort data by column namely "Age"
`df.sort_values(by="Age", ascending=True)`

### 31- Remove rows contain a value for strings and greater(or less) than a value for numbers 
`df=df[df.Name.contains('A')==Flase]` *for special signs like \* use \\**<br>
`df=df[df.Age>100]`

### 32- Depict a general details of columns e.g. count, mean, std, min, etc.
`df.describe()` *for bit shorter info:* `df.info()`

### 33- Depict memory usage of each columns
`df.memory_usage(deep=True)`

### 34- Depict count, mean, std, min, etc of data or each columns
`df.max()` *or* `df.Age.max()` *ro get index of them add arg to them:* `df.argmax()`<br>
`df.Age.value_counts(dropna=False)` *if do not want to count null values, change it to True (default is True) -- for making them normalized, add normalize=True*

### 35- 

