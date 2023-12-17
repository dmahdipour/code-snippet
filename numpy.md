### 1- Install 
`pip install numpy`

### 2- Import
`import numpy as np`

### 3- Define an array (Matrix with 2 rows and 3 columns)
`np.array([[1, 2, 3],[4, 5, 6]])` *If dimentions are not equal, we have list in array insted of numbers:* `np.array([[1, 2, ],[4, 5, 6]])`

### 4- Define an array (Ordinary Numbers)
`np.arange(2, 9, 0.1)` *Start from: 2, end: 10, steps:0.1* <br>
*Use int numbers for step if you want to have integer numbers:* `np.arange(2, 9, 3)` <br>
`np.ones((3,4), dtype=int)` *Whole numbers are 1 and for 1D array:* `np.ones((3))` <ins>default dtype is float</ins> <br>
*To have other numbers (e.g. 5) instead of 1:* `np.full((3,4), 5)` <br>
`np.zeros((3,4), dtyp=int)` *Whole numbers are 0 and for 1D array:* `np.zeros((3))` <br>
`np.eye(3)` *Create ab array with whole 1 in diameter and fill others by 0* <br>
`np.linspace(1,4, num=10)` *Create an 10 items array start from 1 end by 4* <br>
`np.random.random((3,4))` *Create an array with random items between 3 and 4 or get 9 random integer numbers between 0 and 10* `np.random.randint(10, size=9).reshape(3,3)` 

### 5- Change Dimention's size of arrays
`myArray=np.arange(12).reshape(3, 4)` *To revert 2D array to one:* `myArray.reshape(12)` *to convert it in 12 row:* `myArray.reshape(1,12)` <br>
`myArray.flattern()` *Convert any arrays to 1D*

### 6- Update Array's Values
`myArray[2]=30` *or* `myArray[1:4]=10` *To update range of indexes:* `myArray[0:3]` *and for 2D:* `myArray[1][0:3]`

### 7- Get Array's Dimention, Lenghth and Size:
`myArray.ndim` *1 for 1D, 2 for 2D ,etc.* <br>
`myArray.shape` *e.g. (3, 4) - to get rows number:* `myArray.shape[0]` *or* `len(myArray)` *and to get columns number:* `myArray.shape[1]` <br>
`myArray.size` *Get count of whole items. e.g. 12*

### 8- Convert List to Array
```
myList=[[1,2,3],[4,5,6]]
myArray=np.asarray(myList)
```

### 9- Built-in Functions
<ins>*Add axis=0 for finding values throught the columns and axis=1 for rows in 2D array*</ins> <br>
`np.min(myArray, axis=0)` `np.max(myArray)` *Min and Max* <br>
`np.argmin(myArray)` `np.argmax(myArray, axis=1)` *Indexes of Min and Max items* <br>
`np.mean(myArray, axis=1)` *Average of whole items* <br>
`np.median(myArray, axis=0)` *Get an item located in middel of array* <br>
`np.std(myArray, axis=0)` *Standard Deviation of whole items* <br>
`np.sum(myArray, axis=1)` *Sum whole items by columns or rows*

### 10- Indexes and Accesses to item
`myArray[1]` *or for 2D:* `myArray[1,2]` *First index is for row and second one for column* <br>
`myArray[0:2,:]` *Get items in rows 0 to 2 that are in whole columns* <br>
`myArray[:,1:]` *Get items in whole rows but columns start from 1* <br>
`myArray[-3:]` *Get just 3 latest items* <br>
`myArray[:-2]` *Get whole items but 2 latest ones*

### 11- Loops
```
for row in myArray:
  print(row+3)


for row in myArray:
  for item in row:
    print(item*3)
```

### 12- Mathmatics an Logis
`myArray.T` *Transpose* <br>
`myArray+10` *Plus 10 to items one by one. Also, Mines, Multipy, Division, Pow ,etc acan be used.* <br>
`myArray + myArray2` *Sum items of 2 arrays one by one* <br>
`myArray>2` *Get True if our condition are true for each one and vise verse. To get items instead of True/False:* `myArray[myArray>2]` <br>
`np.sqrt(myArray)` *Also Ceil, Sin, Cos, Tan, Arcsin, Arccos, Arctan and etc. can be used.* <br> 
*for more:* https://numpy.org/doc/stable/reference/routines.math.html <br><br>
`myArray.dot(myArray2)` *or* `np.dot(myArray, myArray2)` *or* `np.matmul(myArray, myArray2)` <br>
<ins>*number of column in first array should be equal to number of rows in second one. e.g. 2x**3**  and  **3**x5*</ins> <br><br>
`np.linalg.det(myArray)` *To get Determinant, array should be squar in dimention. This is a kind of Algebra calculation (linalg).*

### 13- Mixup Arrays (Whole arrays should have same dimentions)
`np.vstack((myArray, myArray2))` *Mix to array together Vertically. Rows of second array come under the first one.* <br>
`np.hstack((myArray, myArray2))` *Mix to array together Horizontally. Rows of second array come near the first one.* <br>
