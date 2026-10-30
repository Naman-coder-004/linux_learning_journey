# LINUX BASIC COMMANDS

These are the basic commands I have learned using my linux journey.

# pwd

Displays the current working directory.

# ls

Lists all the files and directories in current directory.

# ls -a

Lists all files, including hidden files.

# ls -l

Lists all files and directories with permissions.

# mkdir

To make a directory.

# rmdir

To delete a directory.

# rm -rf

To forcibly delete a directory and file.

# cd

To enter a directory.

# cd ..

To cache back one directory.

# whoami

To know about the current user.

# touch

To create a empty file.

# cat

To read data in a file.

# head

To print top 10 lines of given file.

# tail

To print bottom 10 lines of given file.

# cp

To copy file/folder from one file/folder to another.

# mv

To move file/folder from one file/folder to another.

To rename file/folder.

# sudo -i

To enter in root user.

# less

To read large file one page at a time.It allows to move both forward and backward.

# more

To read large file one page at a time.It allows to move forward only.

# sudo systemctl status ssh

To check ssh service.

# sudo systemctl start ssh

To start ssh service.

# sudo systemctl stop ssh

To stop ssh service.

# sudo apt install openssh-sever -y

To install ssh server.

# ifconfig

To view ip address.

# ssh username@ipaddress

To take access of anothers ubuntu terminal.
     
           # FILES AND PERMISSIONS

# The chmod Command

`chmod` stands for Change Mode.
It is used to change the permissions of files and directories in Linux.

There are two methods of changing permissions:

1. Numeric Method

2. Symbolic Method
   
# Numeric Method

#read=4

   #write=2
   
   #execute=1
   
   #no permissions=0

# EXAMPLE-

chmod 755 my.txt

chmod 644 my.txt

chmod 700 my.txt

# Symbolic Method

u=user

g=groups

o=others

a=all

# EXAMPLE-

chmod u+w my.txt

chmod u+x my.txt

chmod g+r my.txt

chmod o-w my.txt

chmod a+r my.txt

 `+` Add permission
 
 `-` Remove permission
 
 `=` Set permissions

  # STAT Command
  
Displays detailed information about a file.

# free -h Command

Displays RAM and swap memory usage in a human-readable format.

# Linux Directory Structure

| Directory | Purpose |
|---|---|
| `/` | Root directory |
| `/bin` | Essential commands |
| `/sbin` | System administration commands |
| `/lib` | Essential libraries |
| `/lib64` | 64-bit libraries, where applicable |
| `/boot` | Files needed to start Linux |
| `/dev` | Device files |
| `/etc` | Configuration files |
| `/home` | Regular users' personal files |
| `/root` | Root user's home directory |
| `/mnt` | Temporary mount point |
| `/media` | Removable media mount points |
| `/opt` | Additional software |
| `/tmp` | Temporary files |
| `/usr` | Applications and utilities |
| `/var` | Logs and variable data |
| `/run` | Runtime information |
| `/proc` | Process and kernel information |
| `/sys` | Device and kernel information |
| `/srv` | Data provided by system services |
| `/snap` | Snap package files |
| `/cdrom` | Traditional CD-ROM mount point |
| `/lost+found` | Recovered files on supported filesystems |
| `/media` | Media is a directory used to mount external storage devices such as USB,pendrives,external hard-drive and memory card |
| `/var` | stands for variable.Stores files whose content or size may change frequently while the system is running |


# Users and Groups

# Permissions

Permissions are rules that control who can read, write, and execute a file or directory.

- Read (r): View the contents of a file or list a directory.
  
- Write (w): Modify a file or change directory contents.
  
- Execute (x): Run a file or access a directory.

# sudo

sudo allows an authorized user to run a command with elevated privileges, usually as the administrator (root).
Example:

sudo command

 # User and Group Management
 
Linux is a multi-user operating system. Multiple users can use the same Linux computer, and each user can have different permissions.

- User: An account used to access Linux.
  
- Group: A collection of users.
  
- UID (User ID): A numeric ID that uniquely identifies a user.
  
- Password: Used to authenticate a user when accessing the system.
  
- Home directory: The user's personal directory.
  
- Shell: The command interpreter used to interact with Linux. Examples include bash, zsh, and sh.
- 
   # Create a New User with a Home Directory
  
sudo useradd -m username

The -m option creates a home directory for the new user.

 # Create a New User without a Home Directory
 
sudo useradd username

This creates the account without automatically creating a home directory.

# Create a User and Assign a Shell

To assign Bash while creating a user:

sudo useradd -m -s /bin/bash username
To use another shell, replace /bin/bash with the path to that shell, for example /bin/sh or /bin/zsh if installed.

# Assign a UID to a User

sudo useradd -m -u 1500 -s /bin/bash username

The -u 1500 option assigns UID 1500 to the new user. The UID must be available.

# Set or Change a User's Password

sudo passwd username

Follow the prompts to enter and confirm the password.

 #Switch to Another User
   
su - username

The - starts a login shell and loads the target user's login environment.

To run a single command as another user with administrator authorization, you can also use:

sudo -u username command

# Modify a User's Shell
    
sudo usermod -s /bin/bash username

Replace /bin/bash with the shell you want to assign.

# Change a User's Home Directory

Example: change the user's home directory to /home/vineet and move the existing home-directory contents:

sudo usermod -d /home/vineet -m username

- -d specifies the new home-directory path.
- 
- -m moves the contents of the existing home directory to the new location.
- 
Make sure the target path and username are correct before running the command.

# Lock a User Account

sudo usermod -L username

The -L option locks the user's password authentication.

# Unlock a User Account

sudo usermod -U username

The -U option unlocks the user's password authentication.

# View User Account Information

The /etc/passwd file contains basic account information, including usernames, UIDs, primary group IDs, home directories, and login shells.

cat /etc/passwd

# View Password-Related Account Information

sudo cat /etc/shadow

The /etc/shadow file stores password hashes and password-aging information. Access is restricted because it contains sensitive account data. It does not display users' original plain-text passwords.

# Delete a User
    
sudo userdel username

This deletes the user account but usually leaves the user's home directory and files in place.

# To delete the account and its home directory:

sudo userdel -r username

Use -r carefully because it removes the user's home directory and mail spool where applicable.

### What is a Group?

- A group is a collection of users.
- Groups make it easier to manage permissions for multiple users at once.
- Users can be assigned to groups to control access to files and directories.

---

##  Creating a New Group

# Command:`groupadd`

Creates a new group in Linux.

### Syntax

sudo groupadd groupname 

## Checking Group Membership and Assigned Users

# Command:`getent`

Displays information about a specified group, including its name, group ID, and listed group members.

### Syntax

getent group groupname


## Viewing All Groups

## Command: `cat`

Displays the contents of a file.

### Syntax

cat etc/group

## Viewing the Sudoers Configuration

## Command: `visudo`

The sudoers configuration defines which users and groups can execute commands with elevated privileges.


### Command

sudo visudo

This command opens the sudoers configuration using a syntax-checking editor.

It helps prevent configuration errors that could affect administrative access.


## Adding a User to the Sudo Group

The `usermod` command modifies an existing user account.

### Syntax

sudo usermod -aG sudo username

### Example

sudo usermod -aG sudo naman

This adds the user `naman` to the `sudo` group.

### Explanation

- `sudo` - Runs the command with administrative privileges.
- `usermod` - Modifies a user account.
- `-a` - Appends the group without removing existing supplementary groups.
- `-G` - Specifies supplementary groups.
- `sudo` - The group that grants sudo privileges on a standard Ubuntu installation.
- `username` - The name of the existing user.


  ## Adding a User to Another Group

Use the `usermod` command to add an existing user to a group.

### Syntax

sudo usermod -aG groupname username


### Example

sudo usermod -aG developers naman


This adds the user `naman` to the `developers` group without removing the user's existing supplementary group memberships.

## Changing the Group Ownership of a File or Directory

Command: `chgrp`

Changes the group associated with a file or directory.

### Syntax

sudo chgrp groupname file_or_directory


## Changing the Owner of a File or Directory

Command: `chown`

Changes the owner of a file or directory.

### Syntax

sudo chown owner file_or_directory

## Finding the Location of a Command

Command: `which`

Displays the path of an executable command found through the directories listed in the `PATH` environment variable.


## Locating Binary Files, Source Files, and Manual Pages

Command: `whereis`

Helps locate the binary executable, source files, and manual pages associated with a command.

## Apache Web Server

## Install Apache:

sudo apt install apache2 -y

## Check Apache status:

sudo systemctl status apache2

## Navigate to the default website directory:

cd /var/www/html

###  Editing the Default Webpage

## Using Nano:

sudo nano /var/www/html/index.html


## Using Vim:

sudo vim /var/www/html/index.html

# Compressing and Uncompressing Files

# To install ZIP
sudo apt install zip -y

# To ZIP a file
gzip filename

# To UNZIP a file
gunzip filename.gz

# Another method to ZIP a file
zip abc.zip abc.txt

# Another method to UNZIP a file
unzip abc.zip abc.txt

# TAR Command

# To combine multiple files into a single archive
tar -cvf my.tar my.txt hello.txt

# To extract files from a TAR archive
tar -xvf my.tar

# Output Redirection

It is used to send the output of a command to a file instead of displaying it on the terminal.

### Example

ls >> name.txt

# >>
Previous data will not be deleted. New output will be added to the end of the file.
# >
Previous data will be deleted and replaced with new output.
ls > name.txt

## To Show Errors in a File
ls -asd 2>> name.txt

## To Show Errors and Output
cat abc.txt img.txt &> my.txt

## What is a Cron Job?

A Cron Job is a Linux feature that automatically runs commands or scripts at a scheduled time.


 ## Check Cron Service Status

sudo systemctl status cron

# Use: Checks whether the Cron service is active or inactive.

## List Cron Jobs

crontab -l

# Use: Displays the cron jobs scheduled for the current user.

## Create or Edit Cron Jobs

crontab -e

# Use: Opens the editor to create or modify scheduled cron jobs.

## Remove Cron Jobs

crontab -r

# Use: Removes all scheduled cron jobs belonging to the current user.


## What Is a Process?

- A process is a program that is currently running on a computer.
  

## Types of Processes

# Foreground Process

- A foreground process runs directly in the terminal. The terminal normally waits for the command to finish before accepting another command.

# Example:

sleep 50

- This command waits for 50 seconds and keeps the terminal occupied until it finishes. 

# Background Process

- A background process runs without keeping the terminal occupied, allowing you to enter other commands.

# Example:

sleep 50 &


## Viewing Running Processes

ps

- The ps command displays information about processes.

ps

## Common columns:

- PID: Process ID, a unique identifier for a process.

- TTY: Terminal associated with the process.

- TIME: CPU time used by the process.

- CMD: Command or program name.

## ps aux

- Displays a detailed list of processes running on the system.


## ps -ef

- Displays processes in a full-format listing.


## ps -l

- Displays processes in a long-format listing, including additional information such as process state and priority.


## top

- Displays running processes and updates the information continuously.


## htop

- Provides an interactive view of processes and system resource usage.


-If it is not installed on Ubuntu, install it using:

sudo apt update
sudo apt install htop

Press q to quit.

## pgrep

- Searches for process IDs by process name or another supported pattern.

# Example:

pgrep sleep

- This displays the PIDs of matching sleep processes.


## Killing a Process

kill

- The kill command sends a signal to a process, usually identified by its PID.

kill PID

# Example:

kill 1234



# kill -9

- Forcefully terminates a process using SIGKILL.

kill -9 PID


## killall

Terminates processes by name rather than by PID.

killall process_name

Example:

killall sleep


## Process Priority — nice 

- Linux uses process scheduling priorities to decide how CPU time is shared between runnable processes.

# Nice Value

- The nice value ranges from -20 to +19:


-A lower nice value generally gives a process a greater scheduling priority relative to other processes, while a higher nice value makes it more willing to yield CPU time.

# nice

- The nice command starts a program with a specified nice value.

# Syntax:

nice -n VALUE command

# Example:

nice -n 10 sleep 200

## Disk Management

- Disk management involves checking storage space, monitoring disk usage, viewing partitions, and managing storage devices.

# df — Disk Free

- Displays available and used disk space for mounted file systems.


# df -h — Human-Readable Disk Space

- Displays disk space in an easy-to-read format, such as KB, MB, and GB.

# df -T — File System Type

-Displays the file system type along with disk usage.

# df -i — Inode Usage

- Displays inode usage for mounted file systems. Inodes store information about files and directories.

# df -h / — Root File System Space

- Displays disk space for the file system containing the root directory (/).

# du — Disk Usage

- Shows how much disk space files and directories use.


lsblk — List Block Devices

Displays storage devices and their partitions, such as disks and USB drives.

# lsblk

- To display file system information as well:

lsblk -f

## Mounting and Unmounting

# Mounting

- Mounting means making a storage device or file system accessible at a directory called a mount point.


# Unmounting

- Unmounting detaches a mounted file system so it can be safely disconnected when appropriate.

##  Linux File Systems

-A file system organizes and manages files and directories on a storage device.

# ext3

-An older Linux file system.

# ext4

- A widely used Linux file system.

- Supports large files and volumes.


# XFS

-  High-performance

- Suitable for large files and large storage systems.

# Btrfs

- A modern Linux file system.

Supports features such as snapshots.

##  Networking in Linux

# ifconfig 

- Displays or configures network interfaces on systems where the utility is installed.

# ip addr 

- Displays network interfaces and their IP addresses.


# ping 

- Checks whether a destination responds over the network and displays response times.

ping google.com


# traceroute 

Shows the network hops packets take toward a destination, where intermediate routers respond.

traceroute google.com

## Bash Scripting

- Bash scripting is the process of writing multiple Linux commands in a file and executing them together using the Bash shell. It is used to automate repetitive tasks and simplify system administration.

## Comments in Bash Scripting

- Comments are used to explain code. They are ignored by Bash when the script runs.

The `#` symbol is used to write a single-line comment.


##  Variables in Bash Scripting

A variable is a container used to store data.

### Example

name="Naman"
echo $name


Output:

Naman


### Printing a Sentence Using a Variable

- You can use curly braces to clearly identify a variable inside a string.

  # Example

name="Naman"
echo "My name is ${name}Sharma "

Output:

My name is NamanSharma


##  Special Variables in Bash

- Bash provides special variables that store information about a script and its arguments.

| Variable | Function |
|---|---|
| `$0` | Stores the name or path used to run the script. |
| `$1` | Stores the first argument passed to the script. |
| `$2` | Stores the second argument passed to the script. |

## Bash Operators and Conditions
- These notes cover basic arithmetic operators, if statements, if-else statements, and comparison operators in Bash scripting.
# Arithmetic Operators in Bash
- Arithmetic operators perform calculations on numbers.
- Operator	Meaning
+	Addition
-	Subtraction
*	Multiplication
/	Division
%	Remainder (modulus)

# EXAMPLE

a=10
b=2

echo "Addition: $((a + b))"
echo "Subtraction: $((a - b))"
echo "Multiplication: $((a * b))"
echo "Division: $((a / b))"
echo "Remainder: $((a % b))"

# if Statement
- An if statement runs commands only when a condition is true.
  
# syntax
  if [ condition ]; then
    # commands run if the condition is true
fi

# if-else Statement
- An if-else statement chooses between two paths:
- If the condition is true, the then block runs.
- If the condition is false, the else block runs.

# syntax

if [ condition ]; then
    # commands if true
else
    # commands if false
fi

# Comparison Operators

- Comparison operators compare values.
  
| Operator | Meaning | Example |
|---|---|---|
| `-eq` | Equal to | `[ "$a" -eq "$b" ]` |
| `-ne` | Not equal to | `[ "$a" -ne "$b" ]` |
| `-gt` | Greater than | `[ "$a" -gt "$b" ]` |
| `-lt` | Less than | `[ "$a" -lt "$b" ]` |
| `-ge` | Greater than or equal to | `[ "$a" -ge "$b" ]` |
| `-le` | Less than or equal to | `[ "$a" -le "$b" ]` |


## Symbol Operators in Bash Arithmetic

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |


## Topic : For Loop in Bash Scripting

### Definition
A `for` loop executes a set of commands repeatedly for each item in a specified list.

### Syntax


for i in {1..5}
do
    echo "$i"
done


### Explanation

- `for i in {1..5}` — assigns the numbers 1 to 5 to variable `i`, one at a time.
- `do` — begins the commands to execute.
- `echo "$i"` — prints the current value of `i`.
- `done` — ends the loop.

### Output


1
2
3
4
5


## Topic : Case Statement in Bash Scripting

### Definition
A `case` statement is a conditional statement that selects commands based on the value of a variable.

### Syntax


case $choice in
    pattern1)
        commands
        ;;
    pattern2)
        commands
        ;;
    *)
        commands
        ;;
esac


### Important Points

- `case` starts the statement.
- `$choice` is the variable being checked.
- Each pattern represents a possible matching value.
- `;;` ends a matching case.
- `*)` is the default pattern.
- `esac` ends the statement.

### Example: Check a Day

```bash
echo "Enter a day:"
read day

case $day in
    Monday)
        echo "Start of the working week"
        ;;
    Friday)
        echo "Last working day of the week"
        ;;
    Sunday)
        echo "It's a holiday"
        ;;
    *)
        echo "It's another day"
        ;;
esac


##  Example: Calculator Using Case


echo "Enter first number:"
read a

echo "Enter second number:"
read b

echo "Enter operator (+, -, *, /):"
read op

case $op in
    +)
        echo "Result: $((a + b))"
        ;;
    -)
        echo "Result: $((a - b))"
        ;;
    \*)
        echo "Result: $((a * b))"
        ;;
    /)
        echo "Result: $((a / b))"
        ;;
    *)
        echo "Invalid operator"
        ;;
esac


### What I Learned Today

1. How to use a `for` loop in Bash.
2. How to print a sequence of numbers.
3. How to use a `case` statement.
4. How to handle different inputs using patterns.
5. How to build a simple calculator using Bash.

##  Nested Loop

- A nested loop is a loop inside another loop. The inner loop executes completely for every single iteration of the outer loop.


