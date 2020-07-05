# Creating Directories

`mkdir` command is used to create one or more directories, e.g.:


`mkdir dir1` or `mkdir dir1 dir2 dir3`

###*Options*:
Option|Long Option|Description
------|-----------|-----------
`-p`|`--parent`| Will create all directories leading up to the given directory that doesn't exist already, e.g.: `mkdir -p a/b` will create dir `a` if it doesn't exist, then will create dir `b` inside `a`. If the given directory already exists, ignores the error
`-m`|`--mode`|Specifies octal permission of directories created by `mkdir`
