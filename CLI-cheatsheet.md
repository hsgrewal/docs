# Common CLI Commands

- \>
  - takes the standard output of the command on the left, and redirects it to
    the file on the right

- \>\>
  - takes the standard output of the command on the left and appends it to the
    file on the right

- <
  - takes the standard input from the file on the right and inputs it into the
    program on the left

- |
  - "pipe" takes the standard output of the command on the left, and pipes it
    as standard input to the command on the right. aka command to command
    redirection

- ~/.bash_profile
  - file use to store environment settings. It loads the the contents of the
    bash profile before executing commands when a session starts

- alias
  - allows you to create keyboard shortcuts, or aliases, for command used
    commands

- cd
  - takes a directory name as an argument, and switches into that directory.
    Use directory's path as an argument to navigate directory

- cd ..
  - to move up one directory

- cp
  - copies files or directories

- wildcards (\*)
  - selects all the files in the current directory

- env
  - "environment", and returns a list of the environment variables for the
    current user

- env | grep VARIABLE
  - displays the value of a single environment variable

- export
  - makes the variable to be available to all child sessions initiated from the
    session you are in.

- grep
  - "global regular expression print" searches files for lines that match
    a pattern and returns the results (case sensitive)

- grep -i
  - enables the command to be case insensitive

- grep -R
  - searches all the files in a directory and outputs filenames and lines
    containing matched results. -R stands for "recursive"

- grep -Rl
  - searches all files in a directory and outputs only filenames with matched
    results. -R stands for "recursive" and l stands for "files with matches"

- $HOME
  - variable is an environment variable that displays the path of the home
    directory

- ls
  - lists all files and directories in the working directory

- ls -a
  - lists all contents in the working directory, including hidden files and
    directories

- ls -l
  - lists all contents of a directory in long formant

- ls -t
  - orders files and directories by the time they were last modified

- mkdir
  - takes in a directory name as an argument, and then creates a new
    directory in the current working directory

- mv
  - use source file as the first argument and the destination directory as
    the second argument to move a file into a directory

- vim
  - the **greatest** command line text editor

- $PATH
  - an environment variable that stores a list of directories separated
    by a colon

- pwd
  - prints the name of the working directory

- rm
  - deletes files

- rm -r
  - deletes a directory and all of its child directories

- sed
  - "stream editor" accepts standard input and modifies it based on an
    expression, before displaying it as output data

- sort
  - takes a filename or standard input and orders each line alphabetically,
    printing it to standard output

- touch
  - creates a new file inside the working directory. It takes in a file
    name as an argument, and then creates a new empty file in the current
    working directory

- uniq
  - takes a filename or standard input and prints out every line, removing
    any exact duplicates
