# Copying files/directories

`cp` command used to copy directories and files into other directories, or file content into other file, e.g.:

`cp item1 item2` - copies single file or directory *item1* into file or directory *item2*

`cp file1 file2 dir1` - copies both files into directory dir1


*Some cp options*
Option|Long Option|Meaning
------|-----------|--------- 
-a|--archive|Copy files and directories including all of their attributes like ownership and permissions. Normally copies take on the default attributes of the user performing the copy
-i|--interactive|Before overwriting an existing file user will be prompted for confirmation. **If this option is not specified, cp will overwrite files without warning**
-r|--recursive|Copy directories and their content recursively, this option and `-a` is reguired when copying directories
-u|--update|When copying files from one directory to another one, moves only files that either don't exist or are newer than the existing corresponding files, in the destination directory
-v|--verbose|Display informative messages as the copy is performed


*cp Examples*

`cp dir1/* dir2` - copies all files from dir1 to dir2. Dir2 must already exist.


`cp -r dir1 dir2` - copies content of dir1 to dir2, if dir2 doesn't exist, it is created, and will contain same content as dir1. If dir2 exist, then dir1 will be copied into dir2
