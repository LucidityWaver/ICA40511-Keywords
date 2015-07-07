#PHP Keywords
**Note: PHP Keywords, classes, functions and user-defined functions are not case sensitive

global: Used inside a function to specify that an existing global variable is used in this function. Example below.
```
$x = 5;
$y = 10;
myFunction()
{
    global $x, $y;
    $y = $x + $y;
}
echo $y; //outputs 15;
```
