#LINUX BASIC COMMANDS

These are the basic commands I have learned using my linux journey.

#pwd

Displays the current working directory.

#ls

Lists all the files and directories in current directory.

#ls -a

Lists all files, including hidden files.

#ls -l

Lists all files and directories with permissions.

#mkdir

To make a directory.

#rmdir

To delete a directory.

#rm -rf

To forcibly delete a directory and file.

#cd

To enter a directory.

#cd ..

To cache back one directory.

#whoami

To know about the current user.

#touch

To create a empty file.

#cat

To read data in a file.

#head

To print top 10 lines of given file.

#tail

To print bottom 10 lines of given file.

#cp

To copy file/folder from one file/folder to another.

#mv

To move file/folder from one file/folder to another.

To rename file/folder.

#sudo -i

To enter in root user.

#less

To read large file one page at a time.It allows to move both forward and backward.

#more

To read large file one page at a time.It allows to move forward only.

#sudo systemctl status ssh

To check ssh service.

#sudo systemctl start ssh

To start ssh service.

#sudo systemctl stop ssh

To stop ssh service.

#sudo apt install openssh-sever -y

To install ssh server.

#ifconfig

To view ip address.

#ssh username@ipaddress

To take access of anothers ubuntu terminal.
     
           #FILES AND PERMISSIONS

#The chmod Command

`chmod` stands for Change Mode.
It is used to change the permissions of files and directories in Linux.

There are two methods of changing permissions:

1. Numeric Method

2. Symbolic Method
   
#Numeric Method

#read=4

   #write=2
   
   #execute=1
   
   #no permissions=0

#EXAMPLE-

chmod 755 my.txt

chmod 644 my.txt

chmod 700 my.txt

#Symbolic Method

u=user

g=groups

o=others

a=all

#EXAMPLE-

chmod u+w my.txt

chmod u+x my.txt

chmod g+r my.txt

chmod o-w my.txt

chmod a+r my.txt

 `+` Add permission
 
 `-` Remove permission
 
 `=` Set permissions

  #STAT Command
  
Displays detailed information about a file.

#free -h Command

Displays RAM and swap memory usage in a human-readable format.

#Linux Directory Structure

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






	


 
