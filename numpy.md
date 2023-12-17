### 1- Install 
`pip install numpy`

### 2- Import
`import numpy as np`

### 3- Define an array (Matrix with 2 rows and 3 columns)
`np.array([[1, 2, 3],[4, 5, 6]])` *if dimentions are not equal, we have list in array insted of numbers:* `np.array([[1, 2, ],[4, 5, 6]])`

### 4- Define an array (Ordinary Numbers)
`np.arange(2, 9, 0.1)` *Start from: 2, end: 10, steps:0.1* <br>
*use int numbers for step if you want to have integer numbers:* `np.arange(2, 9, 3)` <br>
`np.ones((3,4), dtype=int)` *whole numbers are 1 and for 1D array:* `np.ones((3))` <ins>default dtype is float</ins> <br>
*to have other numbers (e.g. 5) instead of 1:* `np.full((3,4), 5)` <br>
`np.zeros((3,4), dtyp=int)` *whole numbers are 0 and for 1D array:* `np.zeros((3))` <br>
`np.eye(3)` *create ab array with whole 1 in diameter and fill others by 0* <br>
`np.linspace(1,4, num=10)` *create an 10 items array start from 1 end by 4* <br>
`np.random.random((3,4))` *create an array with random items between 3 and 4*

### 5- Change Dimention's size of arrays
`myArray=np.arange(12).reshape(3, 4)` *to revert 2D array to one:* `myArray.reshape(12)` *to convert it in 12 row:* `myArray.reshape(1,12)`

### 6- Update Array's Values
`myArray[2]=30` *or* `myArray[1:4]=10` *to update range of indexes:* `myArray[0:3]` *and for 2D:* `myArray[1][0:3]`

### 7- Get Array's Dimention, Lenghth and Size:
`myArray.ndim` *1 for 1D, 2 for 2D ,etc.* <br>
`myArray.shape` *e.g. (3, 4) - to get rows number:* `myArray.shape[0]` *or* `len(myArray)` *and to get columns number:* `myArray.shape[1]` <br>
`myArray.size` *display count of whole items. e.g. 12*

### 8- Convert List to Array
```
myList=[[1,2,3],[4,5,6]]
myArray=np.asarray(myList)
```

### 9- Built-in Functions
<ins>*Add axis=0 for finding values throught the columns and axis=1 for rows in 2D array*</ins> <br>
`np.min(myArray, axis=0)` `np.max(myArray)` *get Min and Max* <br>
`np.argmin(myArray)` `np.argmax(myArray, axis=1)` *get Min and Max items indexes* <br>
`np.mean(myArray, axis=1)` *get average of whole items* <br>
`np.median(myArray, axis=0)` *get an item located in middel of array* <br>
`np.std(myArray, axis=0)` *get Standard Deviation of whole items* <br>
`np.sum(myArray, axis=1)` *Sum whole items by columns or rows*

### 10- Indexes and Accesses to item
`myArray[1]` *or for 2D:* `myArray[1,2]` *first index is for row and second one for column* <br>
`myArray[0:2,:]` *get items in rows 0 to 2 that are in whole columns* <br>
`myArray[:,1:]` *get items in whole rows but columns start from 1* <br>
`myArray[-3:]` *get just 3 latest items* <br>
`myArray[:-2]` *get whole items but 2 latest ones*
