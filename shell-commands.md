# Shell-Commands-Documentation

## Basic Directory Commands

**pwd** - Print working directory.

**cd** - Change directory.

**ls** - List items. Lists contents in your current directory.

**ls ..** - Lists the parent directorys files.

**cd .. or cd ./** - Takes you up one level in your directory. You can also think of it as going back in your directory.

**cd ../..** - Takes you up two levels in your directory. You can also think of it as going back two levels or going back twice from your current directory.

**cd .** - Current working directory. Use it to execute scripts.

**cd /** - Changes your directory to the root directory.

**cd ~** - Changes your directory to the home directory.

**cat <filename>** - Concatenates the file you specify to standard output. You could also think of it as displaying the contents of the file.

**touch <filename>** - Allows you to create a file through the shell. Example: **touch test.txt**

**tar** - An archival command that can archive, compress, and extract files, but to make it work, you need to tell which files to take action on, and exactly what to do with those files.
  * Tar can take these arguments (args):
    * **c** - -c for create
    * **z** - -z for zip
    * **f** - -f for file

**echo** - Prints text as STDOUT.

**more** - Display the contents of a file and allows you to scroll through all of its contents.

**less** - Display the contents of file one screen at a time. Also, has the capability of moving forward and backwards when navigating. This command does not need to read the entire file before starting, resulting in faster load times with large files.

**head** - Displays the first part of a file.

**tail** - Displays the last part of a file.

**sudo** - Allows you to do something as a super user. In other words, grants you temporary access for the time being of the command you are trying to execute, but needs root user power in order to do so. **Fun fact** for system administrators **sudo** provides a detailed audit trail so administrators can track what commands individuals used on system files. **Important** Sudo uses a ticketing system where you put in your password once, then you don't have to until you haven't run any sudo commands for five minutes or longer. This is for security reasons just in case you leave your command line open on accident.

**man** - Type **man** to find out which flags a command uses and what they mean, **man** being short for manual. A manual to guide/inform you.

**bin** - Bin, being short for binary is also a standard directory name for executable files or programs.

* **mv** - rename SOURCE to DEST, or move SOURCE(s) to DIRECTORY

  * **mv** [ OPTION ] SOURCE DESTINATION

**xxd** - creates a hex dump of a given file or standar input

**file** - file tests each argument in an attempt to classify it. There are three sets of tests, performed in this order: file system tests, magic tests, and language tests


## Changing File Permissions

**Note:** in order to change the permissions of a file or directory, you must be its owner, be root, or use sudo.

* The **root** user is a super user--- in other words, this user can read, write, delete any file on the system.

* If your are logged in as a non-root user and know the root user's password, you can switch to the root user with the following command: **su -** which will then prompt you for the root user's password. Enter the correct password and you will then be the root user. **Note** root user cannot execute just any file. The file must give have the correct permissions granted in order for a user to do so. If granted, the user can execute.

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

* **chmod +w test.txt**

    * **+w** means "add write access" to the file specified to the right of it which is **test.txt**

## File Operations

**cp <filename>** - Copy from one directory to another. Example:

**cp file1.txt ../anotherDirectory/** - this would allow you to copy file1 in your current directory into the next directory specified in your command which would be **../anotherDirectory/**

**rm <filename>** - Removing a file that you specify with the **rm** command.

**cp * aka asterisk** - Allows you to copy all the files in your current directory.

## Changing context in the Terminal

These commands temporarily provide entirely new tools that can help you to interface more directly with files, to query databases, to experiment with scripting languages such as Ruby and Python, or to otherwise manage your system.

* Database managements commands: **mysql**, **psql**, **redis-client**, **mongo**
  * **mysql** - If you have MySQL installed, typing in this command will connect you with an interface to a MySQL server. **Note** the **mysql** command hijacks commands such as **ls**, **echo**, and **cd**. Only SQL and MySQL commands are available when the MySQL interface is active. Use the command **QUIT** to exit the **mysql** session.

* Text-editors: **vim**, **pico**, **nano**, **emacs**

* REPLs (Read-Eval-Print-Loop), which are basically interactive scripting consoles(basically code in the context of the language you're using inside of the command line): **irb**, **python**, **php -a**

* System monitoring: **top**, **htop**
  * **top** - This command takes over all the available screen and refreshes every 3 seconds shows you all the processes currently running and what state they are currently in such as running, sleeping, and many other things such as memory usage from each application being run. To exit press **Control + C** or **q** to exit **top**

* Reading files or manuals: **man**, **less**, **more**

* Window/Session handling: **byobu**, **screen**, **tmux**
