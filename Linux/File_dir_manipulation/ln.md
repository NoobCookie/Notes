# Hard and Symbolic Links

The `ln` command is used to create hard or symbolic links in the system. It's used in one of two ways.

`ln file [link name]` - to create *hard link*

`ln -s item [link name]` - to create *symbolic link* where *item* is a directory or a file

### Hard links

Hard links are the original Unix way of createing links. By default, every file has a single hard link that gives the file its name. Hard links will still show original file content, even if the original file is removed. Hard links have actual file contents. 
To avoide recursive loops hard links to directories are forbidden on most system. Hard links can be created only to files on the same volume and file system. If the target of hard link is moved the hard link will be automaticly updated and point to new location.
A hard link is indistinguishable from the file itself and, unlike symbolic links, when user lists a directory containing a hard link, he won't see any special indication of the link. Deleting a hard link removes it but the contents of the file iteslf continues to exist, until all links to the file are deleted.

### Symbolic links

Symbolic links were created to overcome limitations of hard links. They are a file that contains a reference to another file or directory in the form of a relative or absolute path.
If a symbolic link is deleted, its target remains unaffected. If a file is deleted before the symbolic link, the link will continue to exist but will point to a non-existing targer.
After creating the symbolic link, it may be treated as an allias for the target. Commands to manage file systems can be used on the symbolic link. Commands that read or write file contents access the contents of target file, while commands that delete or move file work on the link, not target.
