# Current Directory

### Absoluth Pathnames

Aboslute pathname begins with the root directory and follows whole path to the desired directory or file.

Example:
`/usr/bin` - first \/ represents root directory, next is *"usr"* directory which contains a directory called *"bin"*.

### Relative Pathnames

Relative pathname begins in working directory. It requires special notation characters, representing relative position in the file system tree, to do this:

* *"."* - dot notation refers to the working directory.
* *".."* - double dot notation refers to the working directory's parent directory.

Example of changing the parent directory from `/usr/bin`:
1. Using absolute pathname:
 `$ cd /usr`
2. Using relative pathname:
 `$ cd ..`

Example of changing the working directory from `/usr` to `/usr/bin`:
1. Using absolute pathname:
 `$ cd /usr/bin`
2. Using relative pathname:
 `$ cd ./bin`
3. Not declaring any pathname:
 `$ cd bin`
 If a pathname isn't specyfied, the working directory will be assumed. 

### *cd* shortcuts

* `cd` - changes the working directory to home directory
* `cd -` - changes the working directory to previous working directory
* `cd ~user\_name` - changes the working directory to home directory of *user\_name* 
