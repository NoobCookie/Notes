# Move and rename files 

The `mv` command is used both to move files and renaming them, depending on how it's used. In both case, the original filename no longer exists after the operation.

To rename a file or directory:
`mv item1 item2`

To move files:
`mv file1 file2 file3 dir1`

`mv dir1 dir2` - if dir2 doesn't exist, creates dir2 and moves content of dir1 into it, deleting dir1 after. If dir2 does exist, move dir1 and it's content into dir2

The `mv` command shares many options as `cp`
