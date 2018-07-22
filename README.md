# Shell-Commands-Documentation

## Basic Directory Commands

**pwd** - Print working directory.

**cd** - Change directory.

**ls** - List items. Lists contents in your current directory.

**cd ..** - Takes you up one level in your directory. You can also think of it as going back in your directory.

**cd .** - Current working directory. Use it to execute scripts.

## Changing File Permissions

* Each permission within a permission group is assigned a binary representation.

* 4 for read, 2 for write, and 1 for execute.

* These are summed to give the permission for the group.

* Examples: rwx which is r for read, w for write, and x execute looks like this in binary representation, 4 + 2 + 1 which equals 7. Rw is 6, r-x is 5, etc.

* All the individual group permissions are strung together to give an overall permission:

-rw-rw-r-- has a binary permission of 664
-rwx-r-xr-x has a binary permission of 775
