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