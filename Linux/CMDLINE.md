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

Most commands use options consisting of a single character preceded by a dash, e.g.: "-l". Manny commands however, including those from GNU Proect, also support *long options*, which consist of a word preceded by two dashes, e.g.: "--reverse". Also many commands allow for multiple short options to be commbined together.

Example:
`$ ls -lt`

Commands **ls** is given two options "l" to produce long format output and "t" to sort results by file's last modification time.

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






[cd]: ./CD/CD.md
[ls]: ./LS.md
[mkdir]: ./File_dir_manipulation/MKDIR.md
[cp]: ./File_dir_manipulation/CP.md
[mv]: ./File_dir_manipulation/MV.md
[rm]: ./File_dir_manipulation/RM.md
[ln]: ./File_dir_manipulation/LINKS.md
