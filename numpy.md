### 1- Install 
`pip install numpy`

### 2- Import
`import numpy as np`

### 3- Define an array (Matrix with 2 rows and 3 columns)
`myArray=np.array([[1, 2, 3],[4, 5, 6]])` *if dimentions are not equal, we have list in array insted of numbers:* `np.array([[1, 2, ],[4, 5, 6]])`

### 4- Define an array (Ordinary Numbers)
`myArray=np.arange(2, 9, 0.1)` *Start from: 2, end: 10, steps:0.1 - use int numbers for step if you want to have integer numbers:*`np.arange(2, 9, 3)`

### 5- Change Dimention's size of arrays
`myArray=np.arange(12).reshape(3, 4)` *to revert 2D array to one:* `myArray.reshape(12)` *to convert it in 12 row:* `myArray.reshape(1,12)`

### 6- Update Array's Values
`myArray[2]=30` *or* `myArray[1:4]=10` *to update range of indexes:* `myArray[0:3]` *and for 2D:* `myArray[1][0:3]`

### 7- Get Array's Dimention, Lenghth and Size:
`myArray.ndim` *1 for 1D, 2 for 2D ,etc.* <br>
`myArray.shape` *e.g. (3,4) - to get rows number:* `myArray.shape[0]` *and to get columns number:* `myArray.shape[1]` <br>
`len(myArray)` *get count of 1D arrays* <br>
`myArray.size` *display count of whole items. e.g. 12*

### 8- 
