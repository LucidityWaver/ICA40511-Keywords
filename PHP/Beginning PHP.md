#Getting Started with PHP

PHP has been around for a long time. It's likely that our course will use old technologies and styles. [Here](http://www.phptherightway.com/) is a guide to currently recommended usage and styles, with good explanations of some of the core features of PHP. Note: This guide is also available in several other languages.

Much of the information in the above guide is useful for experienced programmers and those already familiar with the basics of PHP. This document is intended to provide information and resources to cover this knowledge gap, so that the guide makes more sense to everyone (myself included).

To begin with take a look at [this file](https://github.com/LucidityWaver/ICA40511-Keywords/blob/master/PHP%20Setup%20%26%20Web%20Server.md) for instructions on, downloading and setting up the latest version of PHP and to learn how to set up the inbuilt PHP Web Server.

###Declaring PHP Code & Statements
PHP opening and closing tags must appear to identify PHP code.

`<?php`
`?> `

Like Java, php statements end with a semi-colon `;`

###Displaying Output
The `echo` and `print` commands in PHP are used for text output. `print` has a return value of 1, so it can be used in expressions. `echo` has no return value, can accept multiple paremeters (although it is rarely used) and is marginally faster than print.

`echo "Hello world";`
`echo "This ", "string ", "was ", "made ", "with multiple parameters.";`

`print "<h2>Hello world!</h2>";`

Note that `print` and `echo` can include html tags.

A short-echo command can be found in php in two forms. `<? ?>` and `<=? ?>`. The first of these is not recommended as it can cause conflicts, such as with xml.

`<=? ?>` can be used when you know that only php versions 5.4 and above will be used. [Click here for more information](http://programmers.stackexchange.com/a/151694).

###Concatenating String Output
As you'll see above, instead of using + to join (concatenate) strings in PHP, a single `.` (dot / period character) is used.

In PHP, you can insert variables to strings without concatenation by including the variable directly in the string. This is called *interpolation*. Both of the following examples achieve the same result, but one is using concatenation and one is using interpolation. As you will see, variables are identified using the dollar symbol `$` character.
```
$msg = "world!"; //variable declaration
echo "Hello $msg";
```
```
$msg = "world!";
echo "Hello " . $msg;
```

When interpolating variables into a String, the variable may need to be surrounded by curly braces `{` `}` so it can be placed directly next to other text.

```
$msg = "world";
echo "Hello {$msg}!;
```

You can also combine the concatenate operator with the assignment operator `.=`
```
$msg = "there";
echo "Hello " . $msg; //output: Hello there
$msg .= ", beautiful world.";
echo "Hello " . $msg; //output: Hello there, beautiful world.
```

###Strings & Literal Strings

Along with double quotations `"`, single quotations `'` can also be used for Strings in PHP.

However, these are considered literal strings as they do not expand escape characters or variables.
```
<?php
$a = "Variables only expand in double quotes.";
echo "This will output as intended. $a \n";
echo 'This will not output as intended\n';
echo ' so this will still be on the same line $a \n.';
?>
```
Output:
```
This will output as intended. Variables only expand in double quotes.
This will not output as intended\n so this will still be on the same line $a \n
```

As with Java and Javascript, you can also use single or double quotation marks inside a String enclosed by the other type.
```
echo "Single quotations are often needed in text, such as to denote a quote or in the possessive form of a name. e.g 'Mary's'";
```

###Nowdoc & Heredoc
PHP v5.3 introduced heredoc and nowdoc syntax. As v5.3 is relatively new, avoid using these when your code may interact with older versions of PHP or when using older versions.

Both of these offer a way to format strings without worrying about concatenating new lines or including new line characters.

Heredoc can be used for literal strings like single quotations `'`.

Nowdoc can be used for Strings like double quotations `"`.

Both are declared using three left angle brackets `<<<` followed by an identifying name. Nowdoc encloses the identifying name in single quotations `'` while heredoc does not. The heredoc or nowdoc ends when the identifying name is repeated on a separate line with no other characters (including spaces) except the semi-colon `;` to terminate the statement.

```
$msg = "Interpolated variable";
$var <<< hDOC
This is the first line of text.
This is the second line of text including an {$msg}.
Third and final line. No concatenation needed.
hDOC;
echo $var;
```

```
$msg = 'As with single line strings, nowdoc is literal. It cannot interpolate variables';
$var <<< nDOC
This is the first line of text.
This is the second line of text including the variable name $msg but not its value.
Third and final line. No concatenation or \n newline characters needed.
hDOC;
echo $var;
```
See **[here](http://www.phptherightway.com/pages/The-Basics.html#strings)** or in the **[php manual](http://php.net/manual/en/language.types.string.php#language.types.string.syntax.heredoc)** for more information and examples on heredoc and nowdoc.

###Commenting
Comments in PHP are similar to Java comments, with `#` and `\\` both denoting single line comments:

```
\\single line comment
#Another type of single line comment
/*Multi-line comment*/
echo "Hello" . /*You can use multi-line comments to block part of a line in PHP */ "world!";
```

###PHP Case Sensitivity
In PHP, **all keywords, classes, functions and user-defined functions are not case-sensitive**. `eCHo` works the same as `EcHo` and `ECHO`.


###Variables
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

###Datatypes
PHP is a *loosely typed* language. This is similar to Javascript and not at all like Java.

In PHP, you will not declare a type for variables as PHP will convert variables to the correct type based on the data they are assigned.

PHP supports the following data types: String, Integer, Float, Boolean, Array, Object, NULL & Resource. 

See [here](http://www.w3schools.com/php/php_datatypes.asp) for more detail on php datatypes such as the maximum integer size.

**Note: Include this information in a separate file later**

Note: There is *almost* no difference with PHP between float, double or `real` as all such values are treated as double by C, which PHP is built from. The gettype() method will return double on a float, but this method shouldn't be used anyway. [More information](http://stackoverflow.com/questions/3280892/difference-between-float-and-double-in-php)

###Variable Scope (Global, local & static)
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

###Common PHP 5 String Functions
These common examples are summarised from the [w3c tutorial](http://www.w3schools.com/php/php_string.asp).
More PHP String functions can be found [on w3c](http://www.w3schools.com/php/php_ref_string.asp) or in the [PHP Manual](http://php.net/manual/en/ref.strings.php)

**Note: An exception is that w3c tutorial is not clear that the replace function replaces ALL instances of that text.**

Get the length of a string using `strlen()` function
```
echo strlen("Hello world!"); //Outputs 12
```

Count the number of words in a string using `str_word_count`
```
echo str_word_count("Hello world!"); // outputs 2
```

Reverse a string
```
echo strrev("Hello world!"); // outputs !dlrow olleH
```

Search for the start position of a substring. Note: The position of the first character in a string is 0, not 1.
```
echo strpos("Hello world!", "world"); // outputs 6
```

Replace part of a string with a different set of characters for every match of a given value.
```
echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!
echo str_replace("world", "Dolly", "Hello world world world!"); // outputs Hello Dolly Dolly Dolly!
```

###Constants
A constant in PHP is an identifier for a value that cannot be changed. Similar to final values in Java.

Constants are not identified with a `$` and are automatically global across the entire script.

A PHP constant is declared using the define function, which has the signature define(*name*, *value*, *case-insensitive*)

The default value for the *case-insensitive* parameter is false.
```
define("PI", 3.1415926535897932384626);
echo PI;
```
As the *case-insensitive* parameter was left out, the default of false was used.
```
define("VERSION", "v0.12", true)
echo vErsIon;
```

###PHP Operators
An overview of operators in PHP can be found on [w3c shools](http://www.w3schools.com/php/php_operators.asp).

One thing that may not be clear is that, due to PHP's loose typing, these operators do not always behave the way you might expect. As an example, performing addtion on two strings does not concatenate the strings.

This is especially true when using comparison operators, such as `==`, `===`, `!=` & `!==`.

When comparing values with `==` or `!=`, PHP performs *type juggling* first so that the values are treated as the same type.
```
$a = "6";
$b = 6;
echo $a == $b; //output: true;
```

PHP will even convert numbers found in strings that do not only contain numbers.

`echo 5 + "10 abdefg"; //output: 15`

This is important as unexpected comparisons against values such as NAN, Null and array() all produce true or false values that may be confusing to debug. Comparisons against NAN always return false, even against itself.

Example of this behaviour can be seen [here](http://www.phptherightway.com/pages/The-Basics.html).

More information can be found in the PHP documentation [here](http://php.net/language.operators.comparison).

I recommend looking at the comparison tables [here](http://php.net/types.comparisons) and bookmarking the page for later reference.

**Another file will be created later for more detail on PHP operators**

One operator you may not be familiar with is the exclusive OR (XOR) operator. XOR tests that only, and only one, one of two conditions are true. If both are true or if neither are true, the expression evaluates false.
'''
echo (4 > 3 XOR 4 > 5); //true, as 4 is greater than 3 (true) and 4 is not greater than 5 (false)
echo (4 < 3 XOR 4 > 5); //false, as 4 is not less than than 3 (false) and 4 is not greater than 5 (false)
echo (4 > 3 XOR 4 < 5); //false, as 4 is greater than 3 (true) and 4 is less than 5 (true)
'''

###PHP if, if...else, if...else-if & switch statements
These statements funtion pretty much identically to Java and Javascript, with the exception of PHP comparison operator concerns noted above in the PHP Operators section. Remember to ensure that the comparisons you intend to make is the comparison your code is performing.

###PHP Loops: while, do...while & for
Pretty much identical to Java & Javascript.
