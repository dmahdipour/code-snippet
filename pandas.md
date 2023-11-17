## Install version 1.1.4
`pip install pandas==1.1.4`

## Import
`import pandas as pd`

## Define data frame (Table with 2 rows and 3 columns
`df=pd.DataFrame([100,101,102],[1,2])`

## Define data frame contain index
`df=pd.DataFrame({'id':[100,101,102], 'color':['red','blue','green']}, index=['a','b','c'])`

## Read csv - xlsx file
`df=pd.read_csv('file-name.csv)`
`df=pd.read_excel('file-name.xlsx)`

## Dipict top 10 rows (default number is 5)
`df.head()`
`df.head(10)`

## 
