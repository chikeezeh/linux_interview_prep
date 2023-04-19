##### When you login you get “$” prompt, what is the prompt for root?
> \# is the default prompt for root. However, this can be changed by editing the `.bashrc` file.
##### Explain the difference between grep and egrep?
>`grep` Stands for global regular expression print, uses basic regular expression, so meta-characters such as `| () {} ?` need to be escaped with `\` when using them in a search pattern.
`egrep` Stands for extended global regular expression print, it uses the >extended regular expression, so meta-characters don't need to be escaped. The
`grep` command can be extended to work like the `egrep` command by using the `-E` flag. See example below, where the pattern is to search for either apple or banana in the file fruits.
``` console
┌──[14:57:20]─[0]─[root@almanode1:~]
└──| grep 'apple|banana' fruits
┌──[14:57:42]─[0]─[root@almanode1:~]
└──| egrep 'apple|banana' fruits
apple
banana
┌──[14:57:49]─[0]─[root@almanode1:~]
└──| grep -E 'apple|banana' fruits
apple
banana
```
##### What is the port # for DNS, NTP and NFS?
>DNS (Domain Named System) Port number 53
NTP (Network Time Protocol) Port number 123
NFS (Network File System) Port number 111 or 2049
These port numbers are assigned by the Internet Assigned Numbers Authority (IANA) and are used as default communication ports for the respective services. 

##### What is the configuration file name of DNS and where is it located?
> `/etc/named.conf`

##### How many new directories will be created after running the following command
```mkdir {a..c}{1..4}```
>12

```console
┌──[15:20:26]─[0]─[root@almanode1:~]
└──| mkdir {a..c}{1..4}
┌──[15:21:20]─[0]─[root@almanode1:~]
└──| ll -d {a..c}{1..4}
drwxr-xr-x. 2 root root 6 Apr 17 15:21 a1
drwxr-xr-x. 2 root root 6 Apr 17 15:21 a2
drwxr-xr-x. 2 root root 6 Apr 17 15:21 a3
drwxr-xr-x. 2 root root 6 Apr 17 15:21 a4
drwxr-xr-x. 2 root root 6 Apr 17 15:21 b1
drwxr-xr-x. 2 root root 6 Apr 17 15:21 b2
drwxr-xr-x. 2 root root 6 Apr 17 15:21 b3
drwxr-xr-x. 2 root root 6 Apr 17 15:21 b4
drwxr-xr-x. 2 root root 6 Apr 17 15:21 c1
drwxr-xr-x. 2 root root 6 Apr 17 15:21 c2
drwxr-xr-x. 2 root root 6 Apr 17 15:21 c3
drwxr-xr-x. 2 root root 6 Apr 17 15:21 c4
```
##### Your PC is configured with a DNS server address but not the default gateway. Can the PC access internet?
>If your PC is configured with a DNS server address but lacks a default gateway, it will not be able to access the internet. The default gateway is essential for routing traffic from your local network to the broader internet.
>
>The DNS server is responsible for resolving domain names into IP addresses. While having a configured DNS server allows your PC to resolve domain names, it still needs the default gateway to send and receive data packets to and from external networks.
>
>In summary, a configured DNS server alone is not sufficient for accessing the internet. You also need a properly configured default gateway to route traffic between your local network and the internet.

##### What is the difference between IP and Gateway
>IP (Internet Protocol) address and gateway are related concepts in computer networking, but they serve different purposes.
>
>IP Address:
An IP address is a unique numerical identifier assigned to each device on a network. It enables devices to communicate with each other within a local network or across the internet. IP addresses can be IPv4 (32-bit) or IPv6 (128-bit) and are typically assigned by a DHCP (Dynamic Host Configuration Protocol) server in most networks.
There are two types of IP addresses:
>
>Private IP addresses: These are reserved for use within local networks and are not routable on the internet. Private IP ranges for IPv4 are 10.0.0.0 - 10.255.255.255, 172.16.0.0 - 172.31.255.255, and 192.168.0.0 - 192.168.255.255.
Public IP addresses: These are globally unique and routable on the internet. Public IP addresses are assigned by an Internet Service Provider (ISP) and enable devices to access the internet.
Gateway:
A gateway is a networking device that connects different networks and allows them to communicate with each other. In the context of home or office networks, the term "default gateway" usually refers to the router that connects your local network to the internet.
The default gateway has its IP address, which is typically a private IP address within the local network's IP range. Devices on the local network use the default gateway to send and receive data packets to and from external networks, such as the internet.
>
>In summary, an IP address is a unique identifier for devices on a network, while a gateway (or default gateway) is a networking device that connects and routes traffic between different networks. Devices use their IP addresses to communicate with each other and the gateway to communicate with external networks.

##### Can you assign one static IP to 2 computers, if not then why?
> No, this will cause an IP conflict.

##### How to change IPs address to static?
>To set a static IP and netmask:
```ifconfig eth0 192.168.1.100 netmask 255.255.255.0```

##### You are trying to ping a server by hostname and you get an error message, “ping: unknown host …”. What could be the reason and how to solve the problem so you can ping it by hostname?

>This could be because the hostname doesn't have a hostname to ip entry on the 
>``` /etc/hosts``` or DNS.

##### Explain the difference between relative and absolute path?
>Absolute path starts from the apex directory which is the ```/``` while a relative path is relative to the current directory.

##### List 3 different methods of adding user?
>```useradd``` command
>```adduser``` command
>Using the GNOME GUI.

##### What is the command to change file/directory ownership and group?
``` chown and chgrp``` commands.

##### List any 3 Type of Linux file systems?
* xfs
* ext4, ext3
* NTFS
* FAT

##### What is /bin directory used for?
> The ```/bin``` directory contains the essential user binaries (programs) that must be present when the
system is mounted in single-user mode. Applications such as Firefox are stored in ```/usr/bin```, while
important system programs and utilities such as the bash shell are located in ```/bin```. The ```/usr```
directory may be stored on another partition – placing these files in the ```/bin``` directory ensures
the system will have these important utilities even if no other file systems are mounted. The
```/sbin``` directory is similar – it contains essential system administration binaries.

##### How do you change a user passwd?
>`passwd username`

##### List any 5 Linux Distribution?
> * Redhat 8/9
> * SUSE
> * Kali Linux
> * Ubuntu
> * Fedora

##### How do you create a directory?
>`mkdir directory_name`

##### How to check Kernel Name?
> `uname -a`
> `hostnamectl`

##### Where are configuration files locate?
> In the `/etc` directory

##### What is the purpose of having different network ports?
So the communication of each application goes through a dedicated port.

##### How do you print the 1st column of a file separated by spaces?
>```console
>    cat filename | awk '{print $1}'
>```

##### How to check your userid and group id?
> While logged in use the `whoami` command to see your user id, then use `id -a userid` to get more information on the user including group id.
> Using the `cat` command on the `/etc/passwd` will show all the users and groups.


##### What is the difference between “kill” and “kill -9” command?
>While kill allows the process to perform some cleanup operations before terminating, kill -9 forcefully terminates the process without giving it a chance to clean up. It is generally recommended to use kill first and only use kill -9 as a last resort, since it may result in data loss or other problems.

##### You are troubleshooting an issue with Redhat support and they have asked you to send the contents of /etc directory. How and which method you will use to transfer the contents?
> Use the `tar` command to create an archive of the `/etc` folder.
> Use a compressing package like `gzip` to compress the archive, then transfer it to RedHat using FTP. The example below combines different folders into one archive.
> ```console
>┌──[19:57:45]─[0]─[root@almanode1:~]
>└──| tar cf folders.tar a1 a2 a3 a4 b1 b2 b3 b4 c1 c2 c3 c4
>```
##### What is root home directory?
>`/root`
##### What is rsyslogd deamon and its purpose?
>rsyslogd is a system daemon that is responsible for receiving and processing system logs on Unix-like operating systems. It is a powerful and flexible syslog implementation that provides several advanced features over the traditional syslog daemon.
>
>The primary purpose of rsyslogd is to collect log messages from various sources such as system services, applications, and hardware devices and route them to the appropriate destination. It allows you to store logs in a variety of formats and can also forward logs to other systems or remote destinations.
>
>Some of the key features of rsyslogd include support for both UDP and TCP protocols, message filtering based on different criteria, log rotation, and the ability to perform real-time message analysis and processing. It also supports various output formats such as plain text, JSON, and CSV, making it easier to analyze logs using different tools and platforms.
>
>Overall, rsyslogd is an essential component of the logging infrastructure on Unix-like systems, and it plays a critical role in ensuring system security, troubleshooting, and performance monitoring.

##### How to check the computer name or host name in Linux?
>`hostname`

##### Which permission allows a user to run an executable with the permissions of the owner of that file?
> The first permission bit must have `x`.

##### What is the command to extract a tarred file?
> `tax xvf /pathtotarfile.tar.gz`

##### What is /proc directory used for?
>The /proc directory is a virtual filesystem in Unix-like operating systems that provides a mechanism for accessing information about running processes and system configuration in real-time. The files and directories in the /proc directory are not actual files on the disk, but rather a view into the system's kernel data structures.
>
>The /proc directory contains a hierarchical structure of numbered directories, each corresponding to a running process on the system. Each of these directories contains a set of files and subdirectories that provide information about the process, such as its status, memory usage, file descriptors, and more.
>
>Apart from process information, the /proc directory also contains files and directories that provide information about system configuration and hardware, including information about CPUs, memory, devices, and more.
>
>Some common use cases of the /proc directory include monitoring system performance, diagnosing issues with processes and system components, and developing system-level tools and utilities.
>
>Overall, the /proc directory is a powerful and essential resource for system administrators and developers on Unix-like systems, providing real-time insights into the inner workings of the system.

##### List 3 basic commands to navigate the filesystem?
> `cd pwd ls`

##### Which service/daemon should be running on the server that allows you to connect remotely?
> `sshd`

##### What is the purpose of firewall?
>A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on a set of predefined security rules. The primary purpose of a firewall is to act as a barrier between a private network (such as a corporate network or home network) and the public Internet or other untrusted networks.

##### What is the difference between memory, virtual memory and cache?
>Memory, virtual memory, and cache are all types of computer memory, but they differ in their purpose, behavior, and characteristics.
>
>Memory, also known as RAM (Random Access Memory), is the physical hardware component of a computer where data and instructions are stored temporarily when a program is running. It is a fast, volatile memory that can be accessed quickly by the processor. Memory is typically measured in gigabytes (GB) or megabytes (MB).
>
>Virtual memory is a technique used by operating systems to expand the amount of available memory beyond the physical limits of the computer's RAM. It allows the system to use hard disk space as an extension of physical memory, by swapping data between the RAM and disk as needed. This allows programs to run even if they require more memory than the system has available. However, virtual memory is slower than physical memory since accessing data on a hard disk is slower than accessing data in RAM.
>
>Cache is a type of memory used by a computer to speed up data access by storing frequently used data or instructions in a location that is faster to access than main memory. It is a smaller, faster memory that is closer to the processor than main memory. Cache is used to reduce the number of times the processor needs to access main memory, which can improve performance. There are different types of cache, including CPU cache, disk cache, and browser cache.

##### How to change a hostname in Linux?
>`hostnamectl set-hostname newhostname`

##### How to check network interfaces in Linux?
>`ip address or ip a`

##### Why is “tail –f logfilename” command used most often and what does it do?
>It will output all incoming logs in real time.

##### How to sort a file in reverse order?
> `cat filename | sort -r`

##### List all byte sizes from smalles to largest?
>* Bit (smallest unit of data)
>* Nibble (4 bits)
>* Byte (8 bits)
>* Kilobyte (KB) (1024 bytes)
>* Megabyte (MB) (1024 KB or 1,048,576 bytes)
>* Gigabyte (GB) (1024 MB or 1,073,741,824 bytes)
>* Terabyte (TB) (1024 GB or 1,099,511,627,776 bytes)
>* Petabyte (PB) (1024 TB or 1,125,899,906,842,624 bytes)
>* Exabyte (EB) (1024 PB or 1,152,921,504,606,846,976 bytes)
>* Zettabyte (ZB) (1024 EB or 1,180,591,620,717,411,303,424 bytes)
>* Yottabyte (YB) (1024 ZB or 1,208,925,819,614,629,174,706,176 bytes)

##### How to check the total number of partition in Linux?
> `fdisk -l or lsblk`

##### What is the exact command syntax to list the 5th column of a file and cut the first 3 letters?
```console
┌──[05:45:59]─[0]─[root@almanode1:~]
└──| cat filename | awk '{print $5}'| cut -c1-3
ber
str
```
##### List any 3 options of ‘df’ command and what they are used for?
>`df -i #shows inode usage`
>`df -h #shows filesytem and disk usage in human readable form`
>`df -a # List [a]ll filesystems, + unreadable, duplicates, pseudo, and inaccessible.`

##### What is the command to change file/directory permissions?
> `chmod`

##### What is the purpose of pipe |?
>To redirect the output of one command as the input to another command.

##### Which command is used to list files in a directory?
> `ls` command is used.

##### There is a command which gives you information about other commands, please explain that command and what is it used for?
> `man` command is an inbuilt manual for commands on the Linux system, it tells you how to use a command.


##### How to delete a file and a directory?
> `rm` command can be used to delete a file, using the `-r` option, you can delete a folder also. `rmdir` can be used to delete an empty folder.

##### What is the difference between “tail” and “tail -10”?
> By default the `tail` command shows the last 10 lines of a file, the `-10` option tells it to show the last 10 also, so there is no difference between the two commands.

##### List 4 commands to display or read a file contents?
> * cat
> * more
> * less
> * vi
##### What are the different commands or methods to write to a file?
> `echo 'content' > file`
> `vi file`
> `cat file1 > file2`

##### What is swap space and how to check swap space?
>Swap space is a reserved storage space that can be used as memory when the machine is out of memory space. You can view the swap space by using the `free -h` command.

##### What is inode and how to find an inode of a file?
> An inode, short for index node, is a data structure used in Unix-based file systems to store information about a file or directory. Each file and directory on a Unix-based file system is associated with an inode, which contains metadata such as the file's owner and permissions, creation and modification times, and the file's location on the disk.
>
>Inodes are used by the file system to track files and directories, and they play a critical role in the file system's ability to efficiently locate and retrieve data. Inodes are allocated when a file or directory is created, and they are typically stored in a fixed area of the file system known as the inode table.
> `ls -i` command can be used to check the inode of a file.

##### Which file to edit for kernel tuning?
>The file to edit for kernel tuning can vary depending on the specific operating system and version you are using. In general, most Linux distributions use the `/etc/sysctl.conf` file to configure kernel parameters at boot time.

##### You have scheduled a job using crontab but it does not run at the time you specified, what could be the reason and how would you troubleshoot?
>Check if the system time is set correctly.
check the crontab entry using `crontab -l` to see if the entry is specified correctly.
check `/var/log/messages` to see if there is an entry for the cron job execution.

##### How to check system hardware information?
>`dmidecode`
##### What is the uniq command used for?
> Output the unique lines from the given input or file.

##### What is the sed command used for?
> A stream editor. Used to perform basic text transformations.
> `command | sed 's/apple/mango/g'` # this replaces apple with mango
>```console
>┌──[14:27:07]─[0]─[root@almanode1:~]
>└──| cat fruits
>apple orange kiwi grape berry
>banana mango carrot spinach strawberry
>┌──[14:27:10]─[0]─[root@almanode1:~]
>└──| cat fruits | sed 's/apple/mango/g'
>mango orange kiwi grape berry
>banana mango carrot spinach strawberry
>```
##### How to view the difference between two files?
>`diff file1 file2`

##### You noticed that one of the Linux servers has no disk space left, how would you troubleshoot that issue?
> If running LVM then add more disk and extend LVM
If not running LVM then add more disk, create a new partition and link the new partition to an existing filesystem.

##### What is a zombie process?
>A zombie process is a process whose execution is completed but it still has an entry in the process table.

##### How do you search for a pattern/word in a file and then replace it in an entire file?
>`sed` command

##### Which command is used to view disk space?
>`df -h`

##### How to create a new group in Linux?
>`groupadd`

##### What is the command to send a message to everyone who is logged into the system?
>`wall`

##### List 4 different directories in /?
> `/bin`
> `/root`
> `/etc`
> `/proc`

##### Which command is used to list the processes?
>`ps -ef`

##### What are the different fields in /etc/passwd file?
>1. Username: This is the name of the user account, which is used to identify the user when logging in.
>
>2. Password: This field used to contain the hashed password for the user account, but on most modern systems it is replaced with a placeholder character, such as an "x". The actual password hash is typically stored in the /etc/shadow file.
>
>3. User ID (UID): This field contains a unique numeric identifier for the user account.
>
>4. Group ID (GID): This field contains the numeric identifier of the primary group for the user account.
>
>5. User Info: This field is used to store additional information about the user, such as their full name or contact information.
>
>6. Home Directory: This field contains the path to the user's home directory, where their files and settings are stored.
>
>7. Login Shell: This field specifies the command or shell that is run when the user logs in. For example, the default login shell on many Unix and Linux systems is the Bash shell (/bin/bash).
> Each field is separated by a `:`.

##### What is the difference between “hostname” and “uname” commands?
> Hostname will give you system name and uname will give you OS information.

##### How to check system load?
> `top` and `uptime` command.

##### How to schedule jobs?
> `crontab` and `at`

##### What are the different fields of a crontab?
>1. Minute: This field specifies the minute of the hour when the task should be executed, and can be any value from 0 to 59.
>
>2. Hour: This field specifies the hour of the day when the task should be executed, and can be any value from 0 to 23.
>
>3. Day of the Month: This field specifies the day of the month when the task should be executed, and can be any value from 1 to 31.
>
>4. Month: This field specifies the month of the year when the task should be executed, and can be any value from 1 to 12, or the first three letters of the month name (e.g. "Jan" for January).
>
>5. Day of the Week: This field specifies the day of the week when the task should be executed, and can be any value from 0 to 7, where 0 and 7 both represent Sunday. Alternatively, the first three letters of the day name can be used (e.g. "Mon" for Monday).
>
>6. Command: This field specifies the command or script that should be executed at the specified time. The command can be any valid Unix command or script, and can include any necessary options or arguments.
>
>The example below will run a command at 11:59 PM on Monday and Thursday.
>```console
>59 23 * * 1,4 command
>```
##### How to restart a service?
> `systemctl restart servicename`

##### How to delete a package in Linux?
> `rpm –e packagename`

##### What is the file name where user password information is saved?
>`/etc/shadow`

##### Which command you would use to find the location of chmod command?
>`which chmod`

##### What is the difference between telnet and ssh?
> ssh is secure where telnet is not

##### List any 4 commands to monitor system?
> top, df –h, iostat, dmesg

##### You are notified that your server is down, list the steps you will take to troubleshoot?
>Check the system physically
Login through system console
Ping the system
Reboot or boot if possible

##### What is the difference between “crontab” and “at” jobs?
>crontab is for repetitive jobs where at is for one time job

##### What is the difference between SAN and NAS?
>SAN (Storage Area Network) and NAS (Network Attached Storage) are both methods of providing centralized storage for multiple devices, but they differ in their architecture, purpose, and implementation.
> * SAN provides block-level access to storage devices, while NAS provides file-level access over a network.
> * SAN requires specialized hardware and software, while NAS is typically easier to set up and use.
> * SAN is used in enterprise environments that require high-speed, low-latency access to large amounts of data, while NAS is used in small to medium-sized businesses or home environments.

##### What is the location of system logs? E.g. messages
> `/var/log`

##### How to setup an alias and what is it used for?
> Edit the `.bashrc` file, and add an alias using the syntax below.
> `alias aliasname='command'`
> Alias is used to create a shortcut to long commands.

##### What is the difference between a process and daemon?
>The main difference between a process and a daemon is that a process is a general term for any running program, while a daemon is a specific type of process that runs in the background and performs a specific task.
