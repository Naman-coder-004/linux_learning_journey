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
     
           FILES AND PERMISSIONS

The chmod Command

`chmod` stands for Change Mode.
It is used to change the permissions of files and directories in Linux.

There are two methods of changing permissions:

1. Numeric Method
2. Symbolic Method
   
Numeric Method
#read=4
   #write=2
   #execute=1
   #no permissions=0

EXAMPLE-
chmod 755 my.txt
chmod 644 my.txt
chmod 700 my.txt

Symbolic Method
u=user
g=groups
o=others
a=all

EXAMPLE-
chmod u+w my.txt
chmod u+x my.txt
chmod g+r my.txt
chmod o-w my.txt
chmod a+r my.txt

- `+` Add permission
- `-` Remove permission
- `=` Set permissions

  STAT Command
Displays detailed information about a file.

free -h Command
Displays RAM and swap memory usage in a human-readable format.

Linux Directory Structure

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









	


 
