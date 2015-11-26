We have been introduced to two forms of arrays in Java.
These notes are on ArrayLists, which you see declared ArrayList<type> arrList = new ArrayList<type>()


When declaring an ArrayList variable, angle brackets <> are used to specify the type of data to be stored in the ArrayList. You cannot use primitive data types such as int, byte or char for an ArrayList type.

```java
ArrayList<Integer> intList; //ArrayList declaration. Integer is the data type and intList is the variable's name.
```

- Java does not require the capacity (length) of an ArrayList when it is initialized.
- The ArrayList is a class with a default constructor that assumes a capacity of 10 if no capacity is given.
- Capacity in an ArrayList is not the same as size. Size is the number of elements which currently exist in the ArrayList and apacity is the maximum number of elements the ArrayList can currently hold.
- Because ArrayList is a class, we are actually creating an ArrayList object during initialization.
```java
intList = new ArrayList<Integer>(); //Initialization of the array with a default length of 10.
intList = new ArrayList<Integer>(15); //Initialization of the array with a specified length of 15.
```
Of course, these statements can be combined as follows:

```java
ArrayList<Integer> intList = new ArrayList<Integer>(15); //ArrayList declared and initialized with a capacity of 15.
```

Additionally, the second set of angle brackets can be left empty (when the compiler can guess or 'infer' the type).

```java
ArrayList<Integer> intList = new ArrayList<>(15); //ArrayList declared and initialized with a capacity of 15.
```

- The above ArrayLists only accept Integer type values.
- An ArrayList of type String would only accept String values.
- An ArrayList of type Object would accept any Object.

ArrayLists cannot be initialized with values in the same way as Arrays. The ArrayList constructor can, however, be passed an array using the Arrays class' asList() method.

```java
ArrayList<Integer> intList = new ArrayList<>(Arrays.asList(10, 15, 20, 25, 30));
```

An existing array can also be passed as an argument.

```java
intList = new ArrayList<>(Arrays.asList(arrayOfIntegers));
```

####Accessing ArrayLists
* Unlike Arrays, values stored in an ArrayList cannot be accessed directly.
* The position of elements in the array is still referred to as an index, starting with 0.
* The ArrayList class includes methods (shown below) to modify the data stored in the ArrayList.
* The ArrayList's add() method has two common overloads.

```java
intList.get(0); //Returns the value in the first position of the ArrayList.
intList.add(15); //Adds 15 to the end of the list.
intList.add(15, 0); //inserts 15 into the list at index 3. Existing elements are moved up a position.
intList.set(15, 3); //replaces the element at position 3 with the value 15.
intList.size() // Returns the number of elements currently in the list.
intList.remove(2) //Removes the element at the specified position.
intList.clear() // Removes all elements from the array.
```
More information can be found in the official documentation [here](http://docs.oracle.com/javase/7/docs/api/java/util/ArrayList.html)

It is important to note that values can only be added into positions that are not beyond the list's current size (the highest existing index position + 1).
Attempting to add a value to position 3 when no value has been given to position 2 will cause an error.

When an ArrayList is created, no default values are set.

Unlike Arrays that cannot change length without manual re-declaration, ArrayLists can change capacity.
If adding an element to an ArrayList would exceed the ArrayList's capacity, Java automatically recreates the ArrayList at a larger capacity.

```java
ArrayList<Integer> intList = new ArrayList<>(2);
intList.add(1); intList.add(2); intList.add(3); intList.add(4);
System.out.println(intList.size()); //Prints 4
```

Loops are often required to work with arrays and ArrayLists.
```java
for (int i = 0; i < intList.size(); i++) {
	System.out.println(intList.get(i)); prints all elements in intList.
}
```

The enhanced for loop works well with ArrayLists when a set of statements are to be executed for every element in the ArrayList.

The following example uses Integer, as the type must match the type stored in the ArrayList (intList).
For each iteration of the loop, the next element from intList is assigned to the variable i (starting from position 0;
```java
for (Integer i : intList) {
	System.out.println(i); prints all elements in intList.
}
```

It may not be clear that the enhanced for loop creates an Integer variable i and assigns it the next value from the ArrayList each iteration of the loop. Two crude examples that may be clearer are given below.
```java
for (int hiddenCounter = 0, Integer i = intList.get(counter); hiddenCounter < intList.size(); hiddenCounter++) {
	System.out.println(i);
}
Integer i; //declaration of i.
for (int j = 0; j < intList.size(); j++) {
	i = intList.get(j); //Assign the value stored
	System.out.println(i);
}
```
In Java, other types of lists (or collections) exist, that are similar to ArrayList.
you can find more information about Java's Collections Framework [here](http://docs.oracle.com/javase/7/docs/technotes/guides/collections/index.html)

ArrayLists in Java can store ArrayLists, creating what is referred to as a multi-dimensional array.
Java (like JavaScript) does not support true multi-dimensional arrays.
For more information, see file ["ArraysOfArrays.md"](https://github.com/LucidityWaver/ICA40511-Keywords/blob/master/Java/ArraysOfArrays.md).
