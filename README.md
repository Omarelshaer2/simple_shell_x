# a simple shell rebuild :
This is a simple UNIX command interpreter written as part of the Alx software engineering course.

### Environment :
Upon invocation, this shell receives and copies the environment of the parent process in which it was executed. This environment is an array of *name-value* strings describing variables in the format *NAME=VALUE*. A few key environmental variables are:

#### HOME
The home directory of the current user and the default directory argument for the **cd** builtin command.

#### PWD
The current working directory as set by the **cd** command.

#### OLDPWD
The previous working directory as set by the **cd** command.

#### PATH
A colon-separated list of directories in which the shell looks for commands. A null directory name in the path (represented by any of two adjacent colons, an initial colon, or a trailing colon) indicates the current directory.

#### cd
  * Usage: `cd [DIRECTORY]`
  * Changes the current directory of the process to `DIRECTORY`.
  * If no argument is given, the command is interpreted as `cd $HOME`.
  * If the argument `-` is given, the command is interpreted as `cd $OLDPWD` and the pathname of the new working directory is printed to standad output.
  * If the argument, `--` is given, the command is interpreted as `cd $OLDPWD` but the pathname of the new working directory is not printed.
  * The environment variables `PWD` and `OLDPWD` are updated after a change of directory.

## Authors :

* Omar Elshaer <[Omar Elshaer](https://github.com/omarelshaer2)>
* Mohammed Ezzat <[mea800](https://github.com/mea800)>

## Acknowledgements :

our simple shell emulates basic functionality of the **sh** shell. This README borrows form the Linux man pages [sh(1)](https://linux.die.net/man/1/sh) and [dash(1)](https://linux.die.net/man/1/dash).

This project was written as part of the curriculum for ALX Africa. ALX Africa SE course is a full-stack software engineering program that prepares students for careers in the tech industry using project-based peer learning. For more information, visit (https://www.alxafrica.com/).
