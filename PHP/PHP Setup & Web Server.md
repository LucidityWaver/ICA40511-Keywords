#Setting up PHP

###Windows Users
For [Windows users](http://windows.php.net/download#php-5.6), just download PHP as the zip folder and unzip it wherever you want your PHP directory. This will only include a standard set-up, and more advanced aspects will require custom compilation or finding a pre-configured version that suits your needs.

Once you have PHP available on your computer, you will need to [set the path environment variables](http://www.computerhope.com/issues/ch000549.htm) to point to the PHP folder. You could also store all your PHP projects in a folder within your PHP folder, but this is a bad idea.

###Mac Users
PHP is bundled with Mac OS X, but may not be up to date. I'll guide you through installation with [Homebrew](http://brew.sh/), but other methods can be found.

1. install Xcode which can be downloaded from the app store.
2. You will need to open the mac terminal application. Terminal can be found in the utilities folder in applications. You can follow this [video guide](https://www.youtube.com/watch?v=zw7Nd67_aFw).
3. Run the command below in terminal. This can also found on the homepage of [Homebrew](http://brew.sh/).

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
4. Run the following four commands in order. [Also found here](https://github.com/Homebrew/homebrew-php#installation)
  1. `brew tap homebrew/dupes`
  2. `brew tap homebrew/versions`
  3. `tap homebrew/homebrew-php`
  4. `brew install php56`

More information for Mac users can be found [here](http://www.phptherightway.com/#mac_setup).


###Setting up a PHP Web Server
PHP, as of version 5.4, comes with an inbuilt web server. This means that you can test PHP code on a website without running additional software such as Apache.

To run the web server, open command line on your computer. For **Windows users** press ctrl+r and type cmd. For **Mac users** running OS X, open your Applications folder, then open the Utilities folder. Open the Terminal application.

The command to run the web server is: `php -S localhost:8000`

*Please ensure you include a capital S in the -S argument.*

###Accessing the Web Server
To access the web server, open your browser and type localhost:8000. You should recieve the message "The requested resource `/` was not found on this server." If this is not working, navigate to the php directory in command line using cd [directory name] to change directories.

###Specify Root Directory
The next step is to specify a root directory/folder for the web server. Include the path information for the root folder after the localhost:8000 argument in your command. Your default root folder is the folder command line is currently pointing to.

`php -S localhost:8000 -t test`

The next step, is to include a php file for the server to read when someone enters the server address. My file test.php contains the following code:

```
<?php
echo "Welcome to PHP";
?>
```

With the root directory test selected and the php web server, entering the address http://localhost:8000/test.php into my web browser displays the message Welcome to PHP.
