###Arrays of Arrays vs Multi-dimensional Arrays
Note that Java uses arrays of arrays to represent multi-dimensional arrays.

Like JavaScript, Java does not actually support multi-dimensional arrays.

Native support for multi-dimensional arrays looks like this: (example from C#)

```C#
int[,] array2D = new int[4, 2] { {1, 2}, { 3, 4 }, { 5, 6 }, { 7, 8 } };
```

It's easy to visualize a multi-dimensional array as a table or matrix.
```
As column-major:
0	1	2	3
1	3	5	7
2	4	6	8
```
```
As row-major:
0	1	2
1	3	4
2	5	6
3	7	8
```

However, in Java and JavaScript, arrays are not strictly multi-dimensional.
This allows you to create jagged arrays.

This also means that arrays are not stored linearly in memory (While Java arrays are stored in sequence in computer memory, memory is not allocated in the same place for a nested array. Each array is stored in different places in memory).

Below is an example in Java. The first part shows the declaration separately from initialization.
* It also demonstrates that you can have a jagged array.
* A jagged array does not have the same amount of columns in every row.

Another visualization can be found [here](http://stackoverflow.com/a/6631081)
```java
int[][] arrOfInts; //Declaration
arrOfInts = new int[5][]; //Initialization of outer 1D array 
arrOfInts[0] = new int[5]; //Initialization of inner (nested) array. Length 5
arrOfInts[1] = new int[3]; //Length 3
arrOfInts[2] = new int[4]; //Length 4
arrOfInts[3] = new int[10]; //Length 10
arrOfInts[4] = new int[2]; //Length 2
```

The above code creates nested int arrays with the following default values.
```
arrOfInts[0] -> 0 0 0 0 0
arrOfInts[1] -> 0 0 0
arrOfInts[2] -> 0 0 0 0
arrOfInts[3] -> 0 0 0 0 0 0 0 0 0 0
arrOfInts[4] -> 0 0
```

Another visualization can be found [here](http://stackoverflow.com/a/6631081)

```java
int[][] arrayOfIntArrays = new int[4][2];
for (int i = 0; i < arrayOfIntArrays.length(); i++) {
	for (int j = 0; j < arrayOfIntArrays[i].length(); j++) {
		arrayOfIntArrays[i][j] = (1+(i*2))+j;
	}
}

int[][] arrayOfIntArrays = new int[4][2] = {
	{1, 2},	{3, 4},
	{5, 6},	{7, 8}
};
```

Multi-dimensional ArrayLists are declared with two data types.
* The first data type is the type of list (collection) that is to be stored.
* The second data type is the data type that can be stored in the list declared as the first data type.

```java
ArrayList<ArrayList<String>> strList = new ArrayList<>();
```
