# Shell-Commands-Documentation

## Basic Directory Commands

**pwd** - Print working directory.

**cd** - Change directory.

**ls** - List items. Lists contents in your current directory.

**cd .. or cd./** - Takes you up one level in your directory. You can also think of it as going back in your directory.

**cd .** - Current working directory. Use it to execute scripts.

**cat <filename>** - Concatenates the file you specify to standard output. You could also think of it as displaying the contents of the file.

**touch <filename>** - Allows you to create a file through the shell. Example: **touch test.txt**

## Changing File Permissions

* Each permission within a permission group is assigned a binary representation.

* 4 for read, 2 for write, and 1 for execute.

* These are summed to give the permission for the group.

* Examples: rwx which is r for read, w for write, and x execute looks like this in binary representation, 4 + 2 + 1 which equals 7. Rw is 6, r-x is 5, etc.

* All the individual group permissions are strung together to give an overall permission:

**-rw-rw-r--** has a binary permission of 664

**-rwx-r-xr-x** has a binary permission of 775

## Listing in Shell

**ls -l** - List in long format. Detailed information on permissions, file size, creation of files, it's location in storage, and the user it's on.

**ls -a** - Shows us everything in the directory, including hidden files. For example, .bashrc which is typically a hidden file.

* You can combine command line switches as well. Example: **ls -la**

## File Permissions

Permissions are in the form **trwxrwxrwx**

* First character is the type of entry:
  * **-** for a file
  * **d** for a directory
  * **l** for a symbolic link

* The three groups: **rwx rwx rwx** list the permissions for the owner, the owner's group, and all users in that order.
  * **r** assigns the read permission
  * **w** assigns the write permission
  * **x** assigns the execute permission
  * **A** in any position denies that permission

Examples:

* **-rw-rw-r--**

  * file, owner and owner's group can read and write and, all other users can only read.   

* **drw-r-----**

    * directory, owner can read and write (add new entries), owner's group can only read, no one else has access.

## File Operations

**cp <filename>** - Copy from one directory to another. Example:

**cp file1.txt ../anotherDirectory/** - this would allow you to copy file1 in your current directory into the next directory specified in your command which would be **../anotherDirectory/**

**rm <filename>** - Removing a file that you specify with the **rm** command.

**cp * aka asteriks** - Allows you to copy all the files in your current directory.
