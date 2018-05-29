# Common CLI Commands

### `\>`
Takes the standard output of the command on the left, and redirects it to the
 file on the right

### `\>\>`
Takes the standard output of the command on the left and appends it to the
file on the right

### `<`
Takes the standard input from the file on the right and inputs it into the
program on the left

### `|`
"pipe" takes the standard output of the command on the left, and pipes it
as standard input to the command on the right. aka command to command
redirection

### wildcards (`\*`)
Selects all the files in the current directory

### `~/.bash_profile`
File used to store environment settings. It loads the the contents of the bash
profile before executing commands when a session starts

### `alias`
Allows you to create keyboard shortcuts, or aliases, for command used commands

### `cat`
Concatenate and print files

##### `-n`
Number lines

### `cd`
Takes a directory name as an argument, and switches into that directory. Use
directory's path as an argument to navigate directory

##### `cd ..`
Move up one directory

##### `cd -`
Jump to previous directory

### `cp`
Copies files or directories

### `env`
"environment", and returns a list of the environment variables for the current
user

##### `env | grep VARIABLE`
Displays the value of a single environment variable

### `export`
Makes the variable to be available to all child sessions initiated from the
session you are in.

### `grep`
"global regular expression print" searches files for lines that match a pattern
and returns the results (case sensitive)

##### `-i`
Enables the command to be case insensitive

##### `-n`
Numbers lines in output

##### `-R`
Searches all the files in a directory and outputs filenames and lines
containing matched results. -R stands for "recursive"

##### `-Rl`
Searches all files in a directory and outputs only filenames with matched
results. -R stands for "recursive" and l stands for "files with matches"

##### `-v`
Ommits lines matching pattern

##### `-E "[LETTERS]"`
Every line with these letters

##### `-E "\w{6,}"`
Every line with 6 or more word chars

### `$HOME`
Variable is an environment variable that displays the path of the home
directory

### `head`
Print first 10 lines of file

##### `-n N`
Specify number of lines

### `less`
Preview files and move around

### `ls`
Lists all files and directories in the working directory

##### `-a`
Lists all contents in the working directory, including hidden files and
directories

##### `-l`
Lists all contents of a directory in long format

##### `-t`
Orders files and directories by the time they were last modified

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

### `sort`
Takes a filename or standard input and orders each line alphabetically,
printing it to standard output

### `tail`
Print last 10 lines of file

##### `-n N`
Specify the number of lines

### `touch`
Creates a new file inside the working directory. It takes in a file name as
an argument, and then creates a new empty file in the current working directory

### `uniq`
Takes a filename or standard input and prints out every line, removing any
exact duplicates

### `wc`
Word count
