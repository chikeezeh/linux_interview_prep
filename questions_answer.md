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
