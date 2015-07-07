#Getting Started with PHP

PHP has been around for a long time. It's likely that our course will use old technologies and styles. [Here](http://www.phptherightway.com/) is a guide to currently recommended usage and styles, with good explanations of some of the core features of PHP. Note: This guide is also available in several other languages.

Much of the information in the above guide is useful for experienced programmers and those already familiar with the basics of PHP. This document is intended to provide information and resources to cover this knowledge gap, so that the guide makes more sense to everyone (myself included).

To begin with take a look at [this file](https://github.com/LucidityWaver/ICA40511-Keywords/blob/master/PHP%20Setup%20%26%20Web%20Server.md) for instructions on, downloading and setting up the latest version of PHP and to learn how to set up the inbuilt PHP Web Server.

PHP opening and closing tags must appear to identify PHP code.

`<?php`
`?> `

The `echo` command in PHP is used for text output.

`echo "Hello world";`

A short-echo command can be found in php in two forms. `<? ?>` and `<=? ?>`. The first of these is not recommended.

`<=? ?>` can be used when you know that only php versions 5.4 and above will be used. [more information](http://programmers.stackexchange.com/a/151694).

Like Java, php statements end with a semi-colon `;`

Comments in PHP are similar to Java comments:

```
\\single line comment
#Another type of single line comment
/*Multi-line comment*/
echo "Helo" . /*You can use multi-line comments to block part of a line in PHP */ "world!";
```

As you'll see above, instead of using + to join (concatenate) strings in PHP, a single `.` (dot / period character) is used.

In PHP, all keywords, classes, functions and user-defined functions are not case-sensitive. `eCHo` works the same as `EcHo` and `ECHO`.

