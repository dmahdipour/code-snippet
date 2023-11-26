### Install version 1.1.4
`pip install pandas==1.1.4`

### Import
`import pandas as pd`

### Define data frame (Table with 2 rows and 3 columns)
`df=pd.DataFrame([100,101,102], [1,2])`

### Define data frame contain index
`df=pd.DataFrame({'id':[100,101,102], 'color':['red','blue','green']}, index=['a','b','c'])`

### Read csv - xlsx file
`df=pd.read_csv('file-name.csv)`<br>
`df=pd.read_excel('file-name.xlsx)`

### Depict top 10 rows (default number is 5)
`df.head()`<br>
`df.head(10)` *or* `df[:10]`

### Depict bottom 10 rows (default number is 5)
`df.tail()`<br>
`df.tail(10)`

### Depict column namely "Age"
`df.Age` *or* `df['Age']`

### Depict 2nd row of column namely "Age"
`df.['Age'][1]`

### Add New Column namely "id" from index values
`df['id']=df.index`

### Copy whole data of df to temp
`temp=df.copy()` *for selecting columns namely A and B:* `temp=df[['A','B']]`

### Shape or Size
`df.shape`

### Convert data to True and False based on being Not Null
`df.notnull()`

### Depict how many Null values are exist
`df.isnull().sum()`

### Count how many 2 values are in column "Age"
`df[df.Age==2].count()`

### Fill Null Values in column "Age" by 2 (for instance)
`df['Age'].fillna(value=2, inplace=True)` *use inplace to make changes applyed - alternatiopn for inplace is:* `df['Age']=df['Age'].fillna(value=2)`

### Remove Null Values in column "Age"
`df['Age'].dropna(how='all', inplace=True)`

### Remove any row contain Null values
`df.dropna(how='any', inplace=True)`

### Remove Column namely "Age"
`df.drop(['Age'], axis=1, inplace=True)`

### Remove Row with index=0
`df.drop(index=0, axis=0, inplace=True)`

### Replace A with another B in Column namely "Name"
`df.Name.replace('A', 'B', inplace=True)` *or* `df.Name=df.Name.replace('A', 'B')`

### Remove "A" from values of Column namely "Name" from right, left and both side of string
*for right:* `df.Name.str.rstrip('A')`<br>
*for left:* `df.Name.str.lstrip('A')`<br>
*for both:* `df.Name.str.strip('A')`

### Change strings to Upper or Lower cases
`df.Name.str.upper()`<br>
`df.Name.str.lower()`

### Count group of values
`df.Age.value_counts()`

### Rename Column namely 'Age' to 'During'
`df.rename(columns={'Age':'During'}, inplace=True)`
#### Rename whole Columns 
`df.columns=['a','b',...]`

### Get columns name and data type
`df.columns` *to show them in list:* `df.columns.tolist()`<br>
`df.dtypes` *or for "Age" column:* `df.Age.dtypes` *'str' is shown as object*

### Conver string dtype of "Age" to float
`df.Age.astype(float)`

### Categorize column "Age" and get codes ang categories' name
`df.Age=df.Age.astype('category')`<br>
`df.Age.cat.codes` *-1 is shown for NaN values*<br>
`df.Age.cat.categories`

### Depict a general details of coulmns e.g. count, mean, std, min, etc.
`df.describe()`
