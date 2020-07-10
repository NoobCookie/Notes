# Linux command line

### Shell prompt

* \$ - user
* \# - superuser privileges active

### Copy and Paste

* Copy - *Ctrl+Shift+C* or *Highlight text + Middle Mouse Button*
* Paste (at cursor position) - *Ctrl+Shift+V* or *Middle Mouse Button*

### File system navigation

Unix-like systems have a single file system tree, regardless of how many storage devices or drives are mounted. They are attached in various points of the tree designated by system administrator.

##### Commands used for navigation

* pwd - Print name of current working diredctory
* cd - [change directory][cd]
* ls - [list directory content][ls]

##### Options and arguments

Most commands in the terminal are followed by one or more *options* that modify their behavior, and further, by one or more *arguments* on which the command acts.

Example syntax:
`command -options arguments`

Most commands use options consisting of a single character preceded by a dash, e.g.: "-l". Manny commands however, including those from GNU Proect, also support *long options*, which consist of a word preceded by two dashes, e.g.: "--reverse". Also many commands allow for multiple short options to be commbined together.

Example:
`$ ls -lt`

Command **ls** is given two options "l" to produce long format output and "t" to sort results by file's last modification time.

*Common ls options*

|**Option**|**Long Option**|**Description**|
-----------|---------------|----------------
| -a | --all | List all filles, even hidden ones |
| -A | --almost-all | Like the `-a` option above except it doesn't list `.`(current directory) and `..`(parent directory) |
| -d | --directory | Lists directory itself not it's content |
| -F | --classify | This option wil append an indicator character to the end of each listed name, e.g. "\/ if the name is a directory |
| -h | --human-readable | In long format listings, displays file size in human readable format than in bytes |
| -l | | Display result in long format |
| -r | --reverse | Display results in reveresed (descending) order |
| -S | | Sort results by files size |
| -t | | Sort by modification time | 

##### File systems

Filenames in Linux are not required to relfect a file's content, while a filename like "picture.jpg" would normally be expected to contain a JPEG compressed image, it's not required to in Linux. To determine what files contain we use the `file` command:

`file filename`

The `file` command will print a brief description of the file's contents, ex.:

```
$ file picture.jpg
picture.jpg: JPEG image data, JFIF standard 1.01
```

One of the common ideas in Unix-like operating systems is that "*everything is a file*".

To view content of a file we can use `less` command.

`less filename`

It start `less` program which allows to scroll forward and backwards through a text file. Contrary to other programs that allow viewing files content, `less` doesn't load whole file at start, which helps with faster loading bigger files.

### Files and directories manipulation

The most frequently used Linux commands, used both for manipulating files and directories, are:

* `cp` - [Copy][cp] files and directories
* `mv` - [Move/rename][mv] files and directories
* `mkdir` - [Create directories][mkdir]
* `rm` - [Remove][rm] files and directories
* `ln` - [Create hard and symbolic links][ln]

Example:
`cp -u *.html destination`

The command above copies all HTML files from one directory to another, but copies only files that don't exist in the destination directory or are newer than the versions in the destination direcotry.

##### Wildcards

Wildcards are a set of special characters that help user specify groups of filenames. Using them (also known as globbing) allows user to select filenames and directories based on patterns of characters.

*Wildcards*
Wildcard|Meaning
--------|-------
`*`|Matches any characters
`?`|Matches any single character
`[characters]`|Matches any character that is a member of the set characters
`[!characters]`|Matches any character that is not a member of the set characters
`[[:class:]]`|Matches any character that is a member of the specified class

*Character Classes*
Character Class|Meaning
---------------|-------
`[:alnum:]` or `[a-zA-Z0-9]`|Matches any alphanumeric character
`[:alpha:]` or `[a-zA-Z]`|Matches any alphabetic character
`[:digit:]` or `[0-9]`|Matches any numeral
`[:lower:]` or `[a-z]`|Matches any lowercase letter
`[:upper:]` or `[A-Z]`|Matches any uppercase letter

*Wildcard examples*
Pattern|Matches
-------|-------
`*`|All files
`g*`|All files starting with "g"
`b*.txt`|Any file starting with "b" followed by any character and ending with ".txt"
`Data???`|Any file starting with "Data" followed by excactly 3 characters
`[abc]`|Any file starting with "a", "b" or "c"
`BACKUP.[0-9][0-9][0-9]`|Any file starting with "BACKUP." followed by excactly 3 numerals
`[[:upper:]]*`|Any file starting with an uppercase letter
`[![:digit:]]*`|Any file not starting with a numeral
`*[[:lower]123]`|Any file ending with a lowercase letter or number "1", "2" or "3"

Wildcards can be used with any command that accepts filenames as arguments and with some graphical file managers.

### Working with Commands

Terminal commands can be divided into four categories:
* **an executable program** - within this category programs can be *compiled binaries* or programs written in *scripting languages*
* **a command built into the shell itself** - number of commands supported by bash, internally called *shell builtins*
* **a shell function** - small scripts incorporated into the enviroment
* **an allias** - aliases are commands that the user can define himself, built from other commands

##### Indentifing Commands

**type -display a command's type**

The `type` command is a shell builtin that displays what kind of command the shell will execute.

`type [command name]`

where "command" is the name of command we want to examin.
Examples:
```
$ type type
type is a shell builtin
$ type ls
ls is alliased to `ls --color=auto`
$ type cp
cp is /bin/cp
```

**which - display an executable's location**

To determine the exact location of a given executable, we use the `which` command.

```
$ which ls
/bin/ls
```

This command works only on executable programs, if we try to use it on a shell builtin or an alias we either get no response or an error message.

**help - get help for shell builtins**

`help` is a built-in facility in bash avaliable for each of the shell builtins.

**--help - display usage information**

Many executable programs support a `--help` option that displays a description of the command's supported syntax and options.

**man - display a program's manual page**

Manual or man page is a formal piece of documentation provided by most executable programs intended for the command line. `man` is a special paging program used to view them. 
Format of manual pages varies but generally they contain the following:
* a title
* a synopsis of the command's syntax
* a description of the command's purpose
* a listing and description of each of the command's options
On most linux systems `man` uses `less` to display the manual page.
To view specific section of the manual user can use `man section search_term`, where section is section number user wants to search.
Example: `$ man 5 passwd`

**apropos - display appropriate commands**

It so possible to search the list of man pages for possible matches based on search term using `apropos` command, e.g.:

```
$ apropos partioion
addpart (8)	- simple wrapper around the "add partiion"...
all-swap (7)	- event signalling that all swap partitions...
```
First field in each line is the name of man page and second field is the section. `man -k` is equivalent to `appropos`.

**whatis - display one-line manual page description**

`whatis` displays the name and one-line description of a man page matching a specified keyword:

```
$ whatis ls
ls		(1)	- list directory content
```

**info - display a program's info entry**

`info` is the GNU Project programs alternative to man pages. They are displeyd with a reader program named "info" their pages are hyperlinked.



[cd]: ./CD/cd.md
[ls]: ./ls.md
[mkdir]: ./File_dir_manipulation/mkdir.md
[cp]: ./File_dir_manipulation/cp.md
[mv]: ./File_dir_manipulation/mv.md
[rm]: ./File_dir_manipulation/rm.md
[ln]: ./File_dir_manipulation/ln.md
