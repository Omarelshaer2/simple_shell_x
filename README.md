# shellby : " a customisable Simple Shell"

A simple UNIX command interpreter written as part of the Alx software engineering course.

### Invocation :
this shell can be invoked both interactively and non-interactively. If **shellby** is invoked with standard input not connected to a terminal, it reads and executes received commands in order.

Example:
```
$ echo "echo 'hello'" | ./shellby
'hello'
$
```

If this shell is invoked with standard input connected to a terminal (determined by [isatty](https://linux.die.net/man/3/isatty)(3)), an *interactive* shell is opened. When executing interactively, **shellby** displays the prompt `$ ` when it is ready to read a command.

Example:
```
$./shellby
$
```

Alternatively, if command line arguments are supplied upon invocation, **shellby** treats the first argument as a file from which to read commands. The supplied file should contain one command per line. **Shellby** runs each of the commands contained in the file in order before exiting.

Example:
```
$ cat test
echo 'hello'
$ ./shellby test
'hello'
$
```

### Environment :
Upon invocation, **shellby** receives and copies the environment of the parent process in which it was executed. This environment is an array of *name-value* strings describing variables in the format *NAME=VALUE*. A few key environmental variables are:

#### HOME
The home directory of the current user and the default directory argument for the **cd** builtin command.

```
$ echo "echo $HOME" | ./shellby
/home/vagrant
```

#### PWD
The current working directory as set by the **cd** command.

```
$ echo "echo $PWD" | ./shellby
/home/vagrant/holberton/simple_shell
```

#### OLDPWD
The previous working directory as set by the **cd** command.

```
$ echo "echo $OLDPWD" | ./shellby
/home/vagrant/holberton/printf
```4

#### PATH
A colon-separated list of directories in which the shell looks for commands. A null directory name in the path (represented by any of two adjacent colons, an initial colon, or a trailing colon) indicates the current directory.

```

#### cd
  * Usage: `cd [DIRECTORY]`
  * Changes the current directory of the process to `DIRECTORY`.
  * If no argument is given, the command is interpreted as `cd $HOME`.
  * If the argument `-` is given, the command is interpreted as `cd $OLDPWD` and the pathname of the new working directory is printed to standad output.
  * If the argument, `--` is given, the command is interpreted as `cd $OLDPWD` but the pathname of the new working directory is not printed.
  * The environment variables `PWD` and `OLDPWD` are updated after a change of directory.

Example:
```
$ ./shellby
$ pwd
/home/vagrant/holberton/simple_shell
$ cd ../
$ pwd
/home/vagrant/holberton
$ cd -
$ pwd
/home/vagrant/holberton/simple_shell
```
#### exit
  * Usage: `exit [STATUS]`
  * Exits the shell.
  * The `STATUS` argument is the integer used to exit the shell.
  * If no argument is given, the command is interpreted as `exit 0`.

Example:
```
$ ./shellby
$ exit
```

#### env
  * Usage: `env`
  * Prints the current environment.

Example:
```
$ ./shellby
$ env
NVM_DIR=/home/vagrant/.nvm
...
```

#### setenv
  * Usage: `setenv [VARIABLE] [VALUE]`
  * Initializes a new environment variable, or modifies an existing one.
  * Upon failure, prints a message to `stderr`.

Example:
```
$ ./shellby
$ setenv NAME Poppy
$ echo $NAME
Poppy
```
## Authors :black_nib:

* Omar Elshaer <[Omar Elshaer](https://github.com/omarelshaer2)>
* Mohammed Ezzat <[mea800](https://github.com/mea800)>
## Acknowledgements :pray:

**Shellby** emulates basic functionality of the **sh** shell. This README borrows form the Linux man pages [sh(1)](https://linux.die.net/man/1/sh) and [dash(1)](https://linux.die.net/man/1/dash).

This project was written as part of the curriculum for ALX Africa. ALX Africa SE course is a full-stack software engineering program that prepares students for careers in the tech industry using project-based peer learning. For more information, visit (https://www.alxafrica.com/).
