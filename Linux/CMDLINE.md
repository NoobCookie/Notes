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

Most commands use options consisting of a single character preceded by a dash, ex. "-l". Manny commands however, including those from GNU Project, also support *long options*, which consist of a word preceded by two dashes, ex. "--reverse". Also many commands allow for multiple short options to be combined together.

Example:
`$ ls -lt`

Command **ls** is given two options "l" to produce long format output and "t" to sort results by file's last modification time.

*Common ls options*

|**Option**|**Long Option**|**Description**|
-----------|---------------|----------------
| -a | --all | List all filles, even hidden ones |
| -A | --almost-all | Like the `-a` option above except it doesn't list `.`(current directory and `..`(parent directory |
| -d | --directory | Lists directory itself not it's content |
| -F | --classify | This option wil append an indicator character to the end of each listed name, ex. "\/" if the name is a directory |
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



[cd]: ./CD/CD.md
[ls]: .LS.md
