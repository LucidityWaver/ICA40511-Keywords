#Getting Started with PHP

PHP has been around for a long time. It's likely that our course will use old technologies and styles. [Here](http://www.phptherightway.com/) is a guide to currently recommended usage and styles, with good explanations of some of the core features of PHP. Note: This guide is also available in several other languages.

Much of the information in the above guide is useful for experienced programmers and those already familiar with the basics of PHP. This document is intended to provide information and resources to cover this knowledge gap, so that the guide makes more sense to everyone (myself included).

To begin with take a look at [this file](https://github.com/LucidityWaver/ICA40511-Keywords/blob/master/PHP%20Setup%20%26%20Web%20Server.md) for instructions on, downloading and setting up the latest version of PHP and to learn how to set up the inbuilt PHP Web Server.

PHP opening and closing tags must appear to identify PHP code.

`<?php`
`?> `

The `echo` and `print` commands in PHP are used for text output. `print` has a return value of 1, so it can be used in expressions. `echo` has no return value, can accept multiple paremeters (although it is rarely used) and is marginally faster than print.

`echo "Hello world";`
`echo "This ", "string ", "was ", "made ", "with multiple parameters.";`

`print "<h2>Hello world!</h2>";`

Note that `print` and `echo` can include html tags.

A short-echo command can be found in php in two forms. `<? ?>` and `<=? ?>`. The first of these is not recommended as it can cause conflicts, such as with xml.

`<=? ?>` can be used when you know that only php versions 5.4 and above will be used. [Click here for more information](http://programmers.stackexchange.com/a/151694).

Like Java, php statements end with a semi-colon `;`

Comments in PHP are similar to Java comments:

```
\\single line comment
#Another type of single line comment
/*Multi-line comment*/
echo "Helo" . /*You can use multi-line comments to block part of a line in PHP */ "world!";
```

As you'll see above, instead of using + to join (concatenate) strings in PHP, a single `.` (dot / period character) is used.

In PHP, **all keywords, classes, functions and user-defined functions are not case-sensitive**. `eCHo` works the same as `EcHo` and `ECHO`.

Variables in PHP are declared by prefixing the `$` dollar character.

```
$msg = "Hello world!";
$i = 9;
$d = 5.5;
```
Notes: [from w3c schools tutorial](http://www.w3schools.com/php/php_variables.asp)
- A variable starts with the $ sign, followed by the name of the variable
- A variable name must start with a letter or the underscore character
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- **Variable names are case-sensitive ($age and $AGE are two different variables)**

In PHP, you can output variables using echo without performing a concatenation using `.`

```
$msg = "world!";
echo "Hello $msg";
```
The following code works the same way:
```
$msg = "world!";
echo "Hello " . $msg;
```

PHP is a *loosely typed* language. This is similar to Javascript and not at all like Java.

In PHP, you will not declare a type for variables as PHP will convert variables to the correct type based on the data they are assigned.

PHP supports the following data types: String, Integer, Float, Boolean, Array, Object, NULL & Resource. Note: There is *almost* no difference with PHP between float, double or `real` as all such values are treated as double by C, which PHP is built from. The gettype() method will return double on a float, but this method shouldn't be used anyway. [More information](http://stackoverflow.com/questions/3280892/difference-between-float-and-double-in-php)

PHP supports local and global variables. Local variables can only be referenced inside the function in which they're declared.

Global variables cannot be used inside a function unless the global keyword is used. Global variables are also stored in an array called `$GLOBALS[]`

A global variable is stored in the `$GLOBALS[]` array by name. A global variable called `$x` can be used from the global array as `$GLOBALS['x']`

In addition, PHP static variables are local variables that stay in memory between function calls. When a function is called a second time, the variable still exists and retains the value from the previous call. See the example below or on the [w3c tutorial](http://www.w3schools.com/php/showphp.asp?filename=demo_var_static)
```
<?php
function myTest() {
     static $x = 0;
     echo $x;
     $x++;
}

myTest();
echo "<br>";
myTest();
echo "<br>";
myTest();
?>  
```

