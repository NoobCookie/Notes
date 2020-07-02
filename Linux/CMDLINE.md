# Linux command line

### Shell prompt

* \$ - user
* \# - superuser privileges active

### Copy and Paste

* Copy - *Ctrl+Shift+C* or *Highlight text + Middle Mouse Button*
* Paste (at cursor positon) - *Ctrl+Shift+V* or *Middle Mouse Button*

### File system navigation

Unix-like systems have a single file system tree, regardless of how many storage devices or drives are mounted. They are attached in various points of the tree designated by system administrator.

##### Commands used for navigation

* pwd - Print name of current working diredctory
* cd - [change directory][cd]
* ls - [list directory content][ls]

##### Options and arguments

Most commands in the terminal are followed by one or more *options* that modify their behavior, and further, by one ore more *arguments* on which the command acts.

Example syntax:
`command -options arguments`

Most commands use options consisting of a single character preceded by a dash, ex. "-l". Manny commands however, including those from GNU Proect, also support *long options*, which consist of a word preceded by two dashes, ex. "--reverse". Also many commands allow for multiple short options to be commbined together.

Example:
`$ ls -lt`

Commands **ls** is given two options "l" to produce long format output and "t" to sort results by file's last modification time.

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

### Files and directoiries manipulation

The most frequently used Linux commands, used both for manipulating files and directories are:

* `cp` - Copy files and directories
* `mv` - Move/rename files and directories
* `mkdir` - Create directories
* `rm` - Remove files and directories
* `ln` - Create hard and symbolic links

Example:
`cp -u *.html destination`

The command above copies all HTML files from one directory to another, but copies only files that don't exist in the destination folder or are newer than the versions in the destination folder.

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



[td]: ./CD/CD.md
[ls]: .LS.md
