###Arrays in Java
We have been introduced to two forms of arrays in Java: Arrays and ArrayLists
These notes are on Arrays which you see declared as int[] arr = new int[5];

In a variable declaration, square brackets [] are placed after the data type to declare an Array of that type.

`int[] arrayOfIntegers; //array declaration. int[] is the data type and arrayOfIntegers is the variable's name.`

Java requires the length of the array when the array is initialized.
The array is not initialized above, only declared.

`arrayOfIntegers = new int[5]; //Initialization of the array with a length of 5.

Of course, these statements can be combined as follows:

`int[] arrayOfIntegers = new int[5]; //array declared and initialized with a length of 5.`

Simple arrays can also be given values when initialized, each value separated by a comma:

`int[] arrayOfIntegers = {4, 2, 1, 4, 7};`

The index refers to the stored position of values within an array, starting with 0.
```
int[0] = 3; //Stores the literal value 3 in position 0 (the first position).
int[3] = 4; //Stores the literal value 4 in position 3 ( the fourth position).
```
As shown above, it is possible to assign values to only some positions in an array and the positions do not have to be assigned values in sequence.

The data type for an array can be any valid data type.
```
String[] arrOfStrings;
Object[] arrOfObjects;
Employee[] arrOfEmployees; //User defined class.
```

When an Array is initialized, the values stored at each index are set to default, or null, values.
```
int[] arrayOfIntegers = new int[5];
System.out.println(arrayOfIntegers[0]); //prints 0, as no value has been assigned.
```
Objects will default to the value 'null'

The length of an Array does not change, unless a new array is initialized.
```
int[] arrayOfIntegers = {4, 2, 1, 4, 7};
System.out.println(arrayOfIntegers[0]); //prints 4
arrayOfIntegers = new int[10];
System.out.println(arrayOfIntegers[0]); //prints 0 as the array has not been assigned values
```

Loops are often required to work with arrays.
A for loop is often used to operate on arrays, as the length of an array is always known.
The loop below counts up from 0 and assigns the value to the corresponding position of the array.
```
for (int i = 0; i < arrayOfIntegers.length; i++) {
	arrayOfIntegers[i] = i;
}
```
####java.util.Arrays
Another method of interacting with an array, is to use the Arrays class provided by Java
The java.util.Arrays class contains static methods that can be used to operate on arrays.

Included in the Arrays class are binarySearch, equals, fill and sort methods.
A version of each method exists for each primitive data type.
binarySearch: can find a value, if it exists, in a sorted array and returns the index position of the value.

`Arrays.binarySearch(arrayOfIntegers, 4); //Searches for the value 4;`

equals: returns true if the two arrays given are equal and false if they are not.

`Arrays.equals(arrayOfIntegers, arrayOfIntegers2);`

fill: replaces the contents of the array with a given value.

`Arrays.fill(arrayOfIntegers, 5); //assigns the value 5 to each position of the array.`

`Arrays.sort(arrayOfIntegers); //Sorts the array into ascending order.`

More information can be found in the official java documentation: http://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html


Arrays in Java can store arrays, creating what is referred to as a multi-dimensional array.
Java (like JavaScript) does not support true multi-dimensional arrays.
For more information, see file "Multidimensional Arrays vs Arrays of Arrays".
