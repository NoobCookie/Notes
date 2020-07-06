# Remove files and directories

The `rm` command is used to remove computer files, directories and symbolic links from a file system, and also special files such as device nodes, pipes and sockets. It uses the *unlink system call* to remove references to objects from the file system. If an object has multiple references, all of them need to be removed before it is discarded. Generally this command does not destroy file data, since it only unlinks references, and file system space freed may still contain data from the removed file.

Example syntax:

`$ rm example`

deletes the file "example" in current user directory

*`rm` options*

Option|Long Option|Meaning
------|-----------|-------
`-i`|`--interactive`|Before deleting any existing file, prompts the user for confirmation for each file. If this option isn't specified, `rm` will delete files silently
`-I`||Prompts user only once for confirmation
`-r`|`--recursive`|Recursively delete directories. Removes a directory and all subdirectories if they exist. This option must be specified to remove any directory
`-f`|`--force`|Ignores nonexisting files and doesn't prompt the user for confirmation. It overrides the `-i` option
`-v`|`--verbose`|Displays informative messages as the deletion is performed
`-d`|`--dir`|Deletes an empty directory, and works only if the directory is empty

**Unix-like systems such as Linux don't have an undo command for deleting objects with `rm`.**
