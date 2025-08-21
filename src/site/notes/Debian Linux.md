---
{"dg-publish":true,"permalink":"/Debian Linux/"}
---


---
# Debian Linux
> [[Operating System\|Operating System]] which was released in the 90s. It is called a [[Linux\|Linux]] distribution since it uses a free & open-source Linux [[OS Kernel\|Kernel]]. 

It was one of the oldest distributions of Linux to go onto the market and was impressively lightweight. It has since formed the foundation of a variety of distributions such as [[Ubuntu\|Ubuntu]] (favoured for being stable and secure) and even [[Kali Linux (Operating System)\|Kali Linux]] (favoured for not having a firewall and aid in [[Ethical Hacking\|Offensive Security]]).  

### Personal Experience
I have extensively used [[Ubuntu\|Ubuntu]] as my daily driver since 2022-2025 and while the computer it was running on still exists and works as of August 2025, due to certain Thermal Issues and service centres in India not being familiar with Linux (as compared to Windows) have caused me to stop using that specific desktop. 

### Terminal & Shell Languages
The shell on Linux is almost always called "Terminal" although many distributions prefer to use different shell languages among bash, sh, zsh, tsh etc.

Although I do not know the details of which languages are used in distributions or whether using a different shell language makes a difference but I have noticed that Debian and Debian-based Distributions all use the same commands which I assume is due to the same shell language used across all derivative distributions.

---
# Commands
One of the foremost commands one must learn on Linux is to use `sudo` which allows the user to temporaily gain Root Access and doing the equivalent of "Running as Administrator" on [[Microsoft Windows\|Microsoft Windows]].

Commands such as `su` stand for switch user.
Using the two we have learnt, one can switch user to sudo by using `sudo su` or switch to another non-root user as `su <username>`.

### Managing Users & User Groups
There are about 100 or so default users. UserID for them go upto 1000. So any user with userID greater than 1000 is non-default. UserIDs are called `uid` for short while user groups have a groupID (`gid`). Users without a group have `uid` equal to their `gid`.

Some of the popular commands:
```bash
sudo adduser <username> # create user
```

```bash
sudo groupadd <groupname> # create group
```

```bash
sudo usermod -aG <groupname> <username> # moves user to group
```

```bash
sudo usermod -g <groupname> <username> # move user to Primary group
# Command makes the group as primary group for users.
```

```bash
sudo groupdel <groupname> # deletes group
# As long as a group is primary for even 1 user, it can't be deleted.
```

### Manage Files & Directories (Folders)
If you wish to create a file from the [[Command Line Interface (CLI)\|Command Line Interface (CLI)]] without using the [[Graphical User Interface (GUI)\|GUI]] at all, your best bet is to use the `echo` command while editing files can be done via the `nano` and `vi` editors in the following way:

```bash
echo <text> > hello.txt # creates hello.txt if not already there
# copies all <text> to hello.txt
```

```bash
cat hello.txt # view the entire file hello.txt
tail hello.txt # view the last few lines of hello.txt
```

```bash
nano hello.txt # edit the file on nano CLI editor
```

```bash
vi sample.txt # opens file in vi editor
# vi is a new editor that is not as simple as nano
# primary problem is being so comfortable with nano that others feel "weird"
# press Esc to exit edit mode & type ":wq!" to save
```

```bash
ip a | grep "string" 
# searches ip addresses that match the "string"
```

Files reside in Directories (Windows calls them Folders)
Directories are created by the `mkdir` command. The following commands deal with creation, management and deletion of directories:

```bash
mkdir <name> # makes a directory named "<name>"
```

```bash
ls # see whatever is inside the directory
```

```bash
ls -ld <name> # check the longlisting and permissions of directory
```

```bash
mkdir <name 1> <name 2> # make two directories
```

```bash
mkdir -p <path> # creates  directory & parent at path (if not already there)
# path must include the name of the folder to be created
```

### File & Directory Permissions
Read, Write and Execute Permissions provided to each directory and file.
Permissions are written in the format `drwxrwxrwx` which can be broken into the following:
1. The first letter can either be `d` or `f` signifying whether these perms belong to a directory or to a file.
2. The first triplet of `rwx` is for the user-owner (`u`) i.e., the user that created and owns the file or directory.
3. The second triplet of `rwx` is for the other users in the same group (`g`) as the user-owner.
4. The last triplet of `rwx` is for any other user (`o`) that does not fit previous criteria.

| short | full    | octal |
| ----- | ------- | ----- |
| r     | read    | 4     |
| w     | write   | 2     |
| x     | execute | 1     |

Using the above arrangement table, we see that users can see two main methods to change permissions, first one being to set it manually using the `rwx` string the other one is to use the octal calculation and the computer comparing the user-given number to 777.

Let's the both the methods in detail:
```bash
chmod u+x <file_name> # provides (+) execute permissions to user
```

```bash
chmod g-w <file_name> # removes (-) write permissions from group
```

```bash
chmod frwxrwxr-x <file_name> # sets 775 perms in string method
chmod 775 <file_name> # sets 775 perms in octal method
```

It is important to note however that execute bit (`x`) is mostly only used in cases for code and to view th output of said code, one must also have the read permissions.

### Network Diagnostics & Backups
```bash
netstat -s # provides network statistics
netstat -tulnp # provides network statistics
```

```bash
tar -cvzf <path> # creates a .tar.gz backup of the directory 
# backup of current dir is created at given path
```

```bash
tar -tvf <path> # extracts a .tar.gz backup from the given path 
# backup is extracted into current directory
```

---
# Footnotes