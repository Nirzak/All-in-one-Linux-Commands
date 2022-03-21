# All Useful Linux Commands In One Place

This whole repository is created to track all the useful linux commands in one place. Created for my own use but you can also star this repository to keep a track on this.

### Table of Contents

---

| No. | Topic                                                                   |
| --- | ----------------------------------------------------------------------- |
| 1   | [**General Commands**](#General-commands)                               |
| 2   | [**File Management Commands**](#File-management-commands)               |
| 3   | [**Text Processing**](#Text-processing)                           |
| 4   | [**Permission Based Commands**](#Permission-commands)                  |
| 5   | [**Networking Commands**](#Networking-commands)                         |
| 6   | [**Package Management Commands**](#managing-packages)                 |
| 7   | [**Memory Usage Commands**](#Memory-usage)                              |
| 8   | [**System and Hardware information**](#system-and-hardware-information) |
| 9   | [**System**](#system)                                                   |

### General Commands

1. **w:** w displays information about currently logged in users and what each user is doing.

   ```bash
    $ w
    23:35:01 up  2:29,  1 user,  load average: 0.72, 1.07, 1.04
    USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
    nirjas   :1       :1               21:04   ?xdm?  34:58   0.01s /usr/lib
   ```

2. **who** Shows information about currently logged in user.

   ```bash
    $ who
    nirjas   :1           2021-11-01 21:04 (:1)
   ```

   Here, from left,
   nirjas - Login Name of the User<br />
   :1 - User terminal<br />
   2021-11-01 21:04 - Date & Time of login<br />

3. **whoami:** Shows the system’s username

   ```bash
    $ whoami
    nirjas
   ```

4. **id:** This command is used to find out user and group names and numeric ID's (UID or group ID) of the current user or any other user in the server.

   ```bash
    $ id
    uid=1000(nirjas) gid=1000(nirjas) groups=1000(nirjas),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),132(lxd),133(sambashare)
   ```

5. **groups:** This command is used to display all the groups for which the user belongs to.

   ```bash
    $ groups
    nirjas adm cdrom sudo dip plugdev lpadmin lxd sambashare
   ```

6. **users:** Displays usernames of all users currently logged on the system.

   ```bash
    $ users
    nirjas
   ```

7. **last:** Displays a list of all last logged in users. The list can be huge according to the number of user logins.

   ```bash
    $ last
    nirjas   :1           :1               Mon Nov  1 21:04    gone - no  logout
    reboot   system boot  5.13.0-20-generi Mon Nov  1 15:06   still running
    nirjas   :1           :1               Mon Nov  1 20:30 - crash  (-5:24)
    reboot   system boot  5.13.0-20-generi Mon Nov  1 20:30   still running
    nirjas   :1           :1               Mon Nov  1 23:53 - down   (-3:24)
    reboot   system boot  5.13.0-20-generi Mon Nov  1 23:53 - 20:29  (-3:23)
    nirjas   :1           :1               Sun Oct 31 23:31 - down   (01:56)
    reboot   system boot  5.13.0-20-generi Sun Oct 31 23:30 - 01:27  (01:56)
   ```

8. **lastlog:** This command is used to find the details of a recent login of all users or a particular user pass through as a flag.

   ```bash
    $ lastlog
    Username         Port     From             Latest
    root                                       **Never logged in**
    daemon                                     **Never logged in**
    bin                                        **Never logged in**
    sys                                        **Never logged in**
    sync                                       **Never logged in**
    games                                      **Never logged in**
    man                                        **Never logged in**
    lp                                         **Never logged in**
    mail                                       **Never logged in**
    news                                       **Never logged in**
   ```

9. **Man:** This command shows the documentation of every command of linux.

   ```bash
    $ man ls
   ```

10. **Date:** Shows date

```bash
 $ date
 Mon Nov  1 11:57:01 PM +06 2021
```

11. **History:** History command shows all the previously used terminal commands in a list.

```bash
 $ history
 1  ls
 2  lspci
 3  lsusb
 4  sudo lspci
 5  sudo apt-get update
 6  sudo apt-get upgrade
 7  lspci
```

12. **whatis:** Whatis shows a short particular information about a command.

```bash
 $ whatis wget
 wget (1)             - The non-interactive network downloader.
```

13. **whereis:** Shows the location of binary, source and manual files for commands.

```bash
 $ whereis ls
 ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
```

14. **alias:** Rename a long repitive command with a short name. For example you can make the command ls -la to any of your suitable name like below example. Then you can use that name to use the command.

```bash
 $ ls -la
 drwxr-xr-x 8 nirjas nirjas 4096 Nov  2 11:25 .
 drwxr-xr-x 4 nirjas nirjas 4096 Nov  2 10:58 ..
 -rw------- 1 nirjas nirjas  765 Nov  2 13:26 .bash_history
 -rw-r--r-- 1 nirjas nirjas  220 Apr 18  2019 .bash_logout
 -rw-r--r-- 1 nirjas nirjas 3564 Oct 27 16:56 .bashrc

 $ alias nr="ls -la"
 $ nr
 drwxr-xr-x 8 nirjas nirjas 4096 Nov  2 11:25 .
 drwxr-xr-x 4 nirjas nirjas 4096 Nov  2 10:58 ..
 -rw------- 1 nirjas nirjas  765 Nov  2 13:26 .bash_history
 -rw-r--r-- 1 nirjas nirjas  220 Apr 18  2019 .bash_logout
 -rw-r--r-- 1 nirjas nirjas 3564 Oct 27 16:56 .bashrc
```

To unalias type,

`unalias <your alias name>`

```bash
 $ unalias nr
```

15. **clear:** Clears the terminal

```bash
 $ clear
```

**[⬆ Back to Top](#table-of-contents)**

### File Management Commands

1. **pwd** The pwd(Present Working Directory) command is used to show current working directory.

   ```bash
    $ pwd
    /home/nirjas
   ```

2. **ls**: The ls command is used to list directories and files. 

   1. Basic command to list files and directories exclusing hidden files:

      ```bash
       $ ls
      ```

   2. List all the files with hidden files and directories that will be denoted as . at the start of the file or directory names.:

      ```bash
       $ ls -a
      ```

   3. Use -la flag to list all the files with their permission details:

      ```bash
       $ ls -la
      ```

3. **mkdir** The mkdir (make directory) command allows users to create directories or folders.

   ```bash
    $ mkdir mydir
    $ ls
    mydir
   ```

   The flag '-p' is used to create multiple directories or parent directories at once.

   ```bash
    $ mkdir -p dir1/dir2/dir3
    $ cd dir1/dir2/dir3
    ~/home/nirjas/dir1/dir2/dir3$
   ```

4. **rmdir**: The rmdir (remove directories) is used to remove empty directories. To delete directories that contains files and fodlers refer to `rm -r directoryName`.

   1. Remove empty directory:

      ```bash
       $ rmdir directoryName
      ```

   2. Remove multiple directories:

      ```bash
       $ rmdir dir1 dir2 dir3
      ```

   3. Remove entire directory tree. This command is similar to `rmdir a/b/c a/b a`:

      ```bash
       $ rmdir -p a/b/c
      ```

5. **rm**: The rm (remove) command is used to remove files, directories, symbolic links etc from the file system.

   1. Remove file: The rm command is used to remove or delete a file.

      ```bash
       $ rm <filename> or <path of file>
      ```

   2. Remove file forcefully: The rm command with -f option is used to remove file without prompting for confirmation.

      ```bash
       $ rm -f filename
      ```

   3. Remove directory: The rm command with -r option is used to remove the directories that contains files. The -r flag is used to delete the contents recursively.

      ```bash
       $ rm -r directoryName
      ```

   4. Remove directory forcefully: The rm command with -rf option is used to forcefully remove directory recursively.

      ```bash
       rm -rf directoryName
      ```

6. **touch**: The touch command is used to create new empty files. Touch is also used to change timestamps on existing files and directories.

   1. **Create a file:** You can create a single empty file using touch command.

      ```bash
       $ touch file1.txt
      ```

   The above command will create a file titled file1.txt.

   2. **Create multiple files:** You can create the multiple numbers of files at the same time.
   
      ```bash
       $ touch file1 file2 file3
      ```

   3. **Change access time:** The touch command with `-a` option is used to change the access time of a file.

      ```bash
       $ touch -a file1.txt
      ```

   4. **Change modification time:** The touch command with `-m` option is used to change the modified time.

      ```bash
       $ touch -m file_name
      ```

   5. **Use timestamp of other file:** The touch command with `r` option is used to get timestamp of another file.

   ```bash
    $ touch -r file2 file1
   ```

   The above command will get the timestamp of file1 and will assign it to file2.

   6. **Create file with Specific time:** The touch command with '-t' option is used to create a file with specified time.

   ```bash
    $ touch -t 1911010000 file_name
   ```

7. **cp**: The cp (copy) command is used to copy files and directories from one location to another location of the system.

   1. Copy file: The cp command is used to copy a file.

      ```bash
       $ cp file1 /home/nirjas/files
      ```

   In this example file1 will be copied to the files directory which is at "/home/nirjas/files" path.

   2. Copy directory: The cp command with -r option is used to copy whole directory with its files recursively.

      ```bash
       $ cp -r directory1 /home/nirjas/myfiles
      ```

   In this example the whole directory1 will be copied to myfiles directory.

   3. Copy files inside directory:

      ```bash
       $ cp -r dir1/* /home/nirjas/myfiles
      ```

   In the above example, all the files inside dir1 will be copied myfiles folder. The dir1 will not be copied. Only the files inside it will be copied. You can also specify which files to copy by the following example.

      ```bash
       $ cp -r dir1/*.txt /home/nirjas/myfiles
      ```

   The above example will copy only text files. 

   4. Copy files without overriding: The cp command with -i will show you interactive prompt to replace if the destination directory already has the file.

      ```bash
       $ cp -i myfile /home/nirjas/files
      ```

8. **mv**: The mv (copy) command usage is almost similar to the cp command and it is used to move or rename files or folders.

   1. Rename files: mv command is also used to rename files in the following way.

      ```bash
       $ mv oldname newname
      ```

   In this example file1 will be copied to the files directory which is at "/home/nirjas/files" path.

   2. Move files:

      ```bash
       $ mv file.txt /home/nirjas/myfiles
      ```

   You can also move mutiple files in one command.

      ```bash
       $ mv file1 file2 file3 /home/nirjas/myfiles
      ```

   3. Move Directories:

      ```bash
       $ mv dir1 /home/nirjas/myfiles
      ``` 

   4. Move files without overriding:

      ```bash
       $ mv -i myfile /home/nirjas/files
      ```

9. **cat**: The cat command is used to view contents of single or multiple files, concatenate files and redirect output in terminal or files.

   ```bash
    $ cat file1 file2
   ```

10. **file**: The file command is used to know the file type.

   ```bash
    $ file file1.txt

    file1.txt: ASCII text
   ```

**[⬆ Back to Top](#table-of-contents)**

### Text Processing

1. **cut**: The cut command is used to extract portion of texts from a file.

   ```bash
    $ cut -c 4 file.txt
   ```

   This will show 4th character from each line of that file. You can also modify it in the follwing way to specify
   your range.

   ```bash
    $ cut -c 4-10 file.txt
   ```

   Here the character range is 4-10.
   To cut off according to fields, -f option is used.

   ```bash
    $ cut -f 2 file.txt
   ```
   By default it uses TABs as the delimiter. so everything separated by a TAB is considered a field.

2. **paste**: The paste command is almost similar to cat command. But instead of just showing the text of the file
it merges the lines of the file in one line. For example suppose `file1.txt` has the below text.

   ```
    Terminal
    is
    awesome
   ```

   Now apply the following command on the text file.

   ```bash
    $ paste -s file1.txt
   ```

   The output will be 'Terminal  is  awesome'. By default it is using TABs as the delimiter.
   But you can set custom delimiter as the following example.

   ```bash
    $ paste -d ' ' -s file1.txt
   ```

   The above example will use spaces the delimiter.

3. **head**: the head command is used the view the first 10 lines of a text file. It's very useful the see the contents of
a huge log files.

   ```bash
    $ head /var/log/syslog
   ```

You can also define how many lines you want to view by the -n option.

   ```bash
    $ head -n 20 /var/log/syslog
   ```

4. **tail**: The tail command is almost similar to the head command. But instead of showing the first 10 lines,
it will show you the last 10 lines as default.

   ```bash
    $ tail /var/log/syslog
   ```

5. **less**: When browsing the long log files you can use another very useful command which is called `less`. If a file content is very large then less is used to view the file contents as a paged manner.

   ```bash
    $ less /var/log/syslog
   ```

   Use the following command to navigate through less: <br />
   q - Used to quit out of less and go back to your shell.<br />
   Page up, Page down, Up and Down - Navigate using the arrow keys and page keys.<br/>
   g - Moves to beginning of the text file.<br />
   G - Moves to the end of the text file. <br />
   /search - You can search for specific text inside the text document. Prefacing the words you want to search with / <br />
   h - If you need a little help about how to use less while you’re in less, use help.

6. **expand and unexpand**: expand is used to convert all the TABs in a text file to spaces.

   ```bash
    $ expand file1.txt
   ```

To convert the spaces back to TABs. Use the unexpand command.

   ```bash
    $ unexpand -a file1.txt
   ```
7. **sort**: The sort command is used to sort the lines in a text file.

   ```bash
    $ sort file1.txt
   ```

To do a reverse sort the -r option is used.

   ```bash
    $ sort -r file1.txt
   ```

8. **tr**: the tr (translate) command is used to translate a set of character to another one.
The following example will convert all lowercase character to uppercase one.

   ```bash
    $ tr a-z A-Z
    terminal
    TERMINAL
   ```

9. **uniq**: Just as the name says it it, the uniq (Unique) command is used to remove all the duplicate texts from a file.

   ```bash
    $ uniq file1.txt
   ```
10. **wc**: The wc command is used to show count of words, lines and bytes from file respectively.

   ```bash
    $ wc file1.txt
   ```

To see only the line counts use the following.

   ```bash
    $ wc -l file1.txt
   ```
Similarly, -w, -c can be used to show only count of words and bytes respectively.

11. **grep**: When it comes to text processing or filtering results of other commands, grep is probably the most used
command in such cases. The main syntax is following.

   ```bash
    $ grep pattern file
   ```

You can also defines the patterns that are case sensitive by -i flag.

   ```bash
    $ grep -i pattern file
   ```

Grep can also be used with commands as a pipeline.

   ```bash
    $ ls /nirjas/home | grep -i file1
   ```

The above command will show the file1 from /nirjas/home directory.
To search for the lines which doesn't contain the particular keyword use the -v option.

   ```bash
    $ ps aux | grep -v grep
   ```

The above example will ignore all the grep processes and shows the others. 

Grep can also be used with regular expressions.

   ```bash
    $ grep "one$" file1.txt
   ```

The above command will show the lines which are ending the word `one`.
Some other useful regular expressions with grep are as follows.

   1. Matching any character: To match any character with a particular word the period (.) is used.

      ```bash
       $ grep "..rent" file.txt
      ```

   The above command will match anything that has two characters and then the string `rent`

   2. Bracket Expressions: You can also specify mutiple words with a particular character by enclosing them
   with a bracket.

      ```bash
       $ grep "swe[ea]t" file.txt
      ```

   The above command will match this two words `sweet` and `sweat`

   To find every line which starts with a capital letter,

      ```bash
       $ grep "^[A-Z]" file.txt
      ```

   Instead of using character ranges POSIX classes can also be used for the above example,

      ```bash
       $ grep "^[[:upper:]]" file.txt
      ```

   To find each line that contains an opening and closing parenthesis, with only letters and single spaces in between, the following expression can be used,

      ```bash
       $ grep "([A-Za-z ]*)" file.txt
      ```

   To escape meta characters, the backslash character (\) in front of the characters are used.

      ```bash
       $ grep "^[A-Z].*\.$" file.txt
      ```

   The above example will find any line that begins with a capital letter and ends with a period. But it escapes the ending period so that it represents a literal period.

   3. Extended Regex: To use extended regular expression the -E option is used.
   To group multiple expressions, enclose them in a paratheses. 

   ```bash
    $ grep -E "(Color|Colour)" file.txt
   ``` 

   The above example will find either `Color` or `Colour` from the text.

   To find any words between chracter range, enclose the range with `{ }` brackets.

   ```bash
    $ grep -E "[[:alpha:]]{5,10}"
   ```
   The above command will find all words that have between 5-10 characters. 

   To ignore any lines that are commented or blank use the following grep command,

   ```bash
    $ sudo grep -vE '^(#|$)'
   ```

   It's very useful to find lines in a big configuration file.


### Permission Commands

Linux has four types of permissions.

   r = read

   w = write

   x = execute

   \- = no permission

Each file and directory has three types of owners.
i. **User:** Owner of the file who created it.
ii. **Group:** Group of users with the same access permissions to the file or directory.
iii. **Other:** Applies to all other users on the system

**Changing Permission:**

The `chmod` command is used to change file or directory permissions. There are two types of usage of this command.

1. **Absolute mode:** In this mode file permission is represented by an octal value.
The numeric representation of the values are the following.
- 4: read permission
- 2: write permission
- 1: execute permission

```bash
 $ sudo chmod 755 myfile
```

The above commands means the following.
7 = 4 + 2 + 1, 7 is the user permissions and it has read, write and execute permissions

5 = 4 + 1, the group has read and execute permission

5 = 4 + 1, and all other users have read and execute permissions

2. **Symbolic mode:** In this mode permissions can be changed for specific owners.
The owners are represented in below table.

   | Owner | Description |
   | ----- | ----- |
   | u | user/owner |
   | g | group |
   | o | other |
   | a | all |

The permissions can be add, remove and assign by using mathematical symbols like as below.

- `+` : Add permission
- `-` : remove permission
- `=` : Assign permission

```bash
 $ chmod u+x file
```

The above command will add execute permission to user. Similarly, You can add or remove permission like below examples.

```bash
 $ chmod u-x file
```

Removes execute permission from user.

```bash
 $ chmod ug+x file
```

Adds execute permission to both user and group.

```bash
 $ chmod g-w file
```

Removes write permission from group. 

```bash
 $ chmod o+r file
```

Add read permission to others. 

**Changing Ownership:**

**1. User ownership:** User ownership can be updated by using the `chown` command.

```bash
 $ chown user file
```

or,

```bash
 $ chown username:groupname file
```

**2. Group ownership:** Group ownership can be modified by using the `chgrp` command.

```bash
 $ chgrp groupname file
```

**[⬆ Back to Top](#table-of-contents)**


### Networking Commands

1.  **ifconfig:** The `ifconfig` command is used to display and configure all network interfaces.

```bash
 $ ifconfig -a
```

To create an interface and bring it up use the following command.

```bash
 $ ifconfig eth0 192.168.0.1 netmask 255.255.255.0 up
```

2. **ifup and ifdown:**

```bash
 $ ifup eth0
 $ ifdown eth0
```

ifup is to enable a network device and ifdown will disable it.

3. **ip command:** the `ip` command is a versatile command and is the replacement for both `ifconfig` command
and `route` command. It can be used for mutiple puposes.

   1. **Showing interfaces:** Equavalent to `ifconfig` command.

      ```bash
       $ ip link show
      ```

   2. **Showing interface statistics:** 

      ```bash
       $ ip -s link show eth0
      ```

   3. **Showing ip address assigned to interfaces:** 

      ```bash
       $ ip address show
      ```
   or,

      ```bash
       $ ip addr show
      ```

   4. **To bring interfaces up and down:** Equlavalent to `ifup` and `ifdown` command

      ```bash
       $ ip link set eth0 up
       $ ip link set eth0 down
      ```

   5. **Add an IP address to an interface:** 

      ```bash
       $ ip address add 192.168.0.1/24 dev eth0
      ```

   6. **Showing routing table:** Equavalent to `route` command.

      ```bash
       $ ip route list
      ```

   7. **Add a route:** Equavalent to `route add` command.

      ```bash
       $ ip route add 192.168.0.1/24 via 10.10.12.3
      ```

   8. **Remove a route:** Equavalent to `route del` command.

      ```bash
       $ ip route delete 192.168.0.1/24
      ```

4. **route command:** The `route` command is used to command is used to show, add or delete routes.

   1. **Showing routing table:** Equavalent to `route` command.

      ```bash
       $ sudo route -n
      ```

   2. **Add a route:** Equavalent to `ip route add` command.

      ```bash
       $ sudo route add -net 192.168.0.1/24 gw 10.10.12.3
      ```

   3. **Remove a route:** Equavalent to `ip route delete` command.

      ```bash
       $ sudo route del -net 192.168.0.1/24
      ```

5. **ping:** the `ping` command is used to check whether a packet can reach to the destination host or not.

```bash
 $ ping google.com
```

6. **whois:** The `Whois` command is used to get whois information of a domain.

```bash
 $ whois google.com
```

7. **traceroute:** The `traceroute` command is used to see how packets are getting routed.

```bash
 $ traceroute google.com
```

8. **netstat:** The `netstat` command is used to show the detailed information about the network.
for more info run `man netstat` command on terminal.

```bash
 $ netstat -at
```

To view the active ports of the device use the following command.

```bash
 $ netstat -pnltu
```

9. **tcpdump:** The `tcpdump` is to monitor packet activities. It will not be available by default in the operating
system. It can be installed by `sudo apt install tcpdump` command.

```bash
 $ sudo tcpdump -i wlan0
```

10. **dig:** The `dig` command is used to view the DNS information. It is equavalent to `nslookup` command.

```bash
 $ dig www.google.com
```

11. **nslookup:** The `nslookup` command can be also useful in case of DNS information. It is equavalent to `dig` command.

```bash
 $ nslookup www.google.com
```

12. **nmcli:** `nmcli` command allows one to control and modify NetworkManager.

      1. **Overall status of Networkmanager:** To check overall status of the networkmanager. use the following command.

         ```bash
          $ sudo nmcli general status 
         ```

      2. **Viewing all connections:** To view all connections of the PC.

         ```bash
          $ sudo nmcli connection show 
         ```

      3. **Detailed information about a connection:** To view detail information about a connection

         ```bash
          $ sudo nmcli -p connection show connection-name
         ```

      4. **Adding an interface:** To add an interface device type the following command.

         ```bash
          $ sudo nmcli connection add ifname <interface-name> type <connection-type> con-name <connection-name> ipv4.addresses <ip with subnet mask> ipv4.gateway <gateway> ipv4.dns <dns> ipv4.method <method>
         ```

         For example to set e static IP we will use the following command.

         ```bash
          $ sudo nmcli connection add ifname enmp0s3 type ethernet con-name enp0s3 ipv4.addresses 192.168.0.108/24 ipv4.gateway 192.168.0.1 ipv4.dns 8.8.8.8 ipv4.method manual
         ```

      5. **Modifying an interface:** To modify an interface use the following command.

         ```bash
          $ sudo nmcli connection modify enp0s3 ipv4.addresses 192.168.0.110/24
         ```

      6. **Changing wifi on or off:** Turning wifi on or off.

         ```bash
          $ sudo nmcli radio wifi (on or off )
         ```

      7. **Up or Down a connection:** To enable or disable a connection.

         ```bash
          $ sudo nmcli connection up connection-name
         ```

         ```bash
          $ sudo nmcli connection down connection-name
         ```

      8. **Viewing list of wifi connections:** To view the list of all nearby wifi connections.

         ```bash
          $ sudo nmcli device wifi list
         ```

      9. **Viewing connected WiFi Password:** To view the stored password of an active wifi connection.

         ```bash
          $ sudo nmcli device wifi show-password
         ```

Nmcli is a most versatile terminal command and the most useful also. For more usage information use `man nmcli` command.

13. **dhclient:** The `dhclient` command is used to obtain a fresh IP from the DHCP server.

```bash
 $ sudo dhclient
```

14. **arp:** The `arp` command is used to show the arp cache of your device. 

```bash
 $ arp -a
```

15. **hostname:** `hostname` command can be usedful to view the device IP.

```bash
 $ hostname -I
```

16. **nmap:** The `nmap` command is used to scan open services and ports of a server.

```bash
 $ nmap -A www.nirzash.me
```
To view the firewall setting with all information use the following command.

```bash
 $ nmap -sA www.nirzash.me
```

**[⬆ Back to Top](#table-of-contents)**

### Managing packages

1. **Install package:**

```bash
 $ sudo yum install package_name
```

2. **Package description:**
The info command is used to display brief details about a package.

```bash
 $ yum info package_name
```

3. **Uninstall package:**
The remove command is used to remove or uninstall package name.
```bash
 $ sudo yum remove package_name
```

4. **Package dependencies:**
The deplist command is used to display the dependencies of a package.

```bash
 $ yum deplist package_name
```

5. **Search for packages:**
To search for packgaes use the following command.

```bash
 $ yum search keyword
```

6. **Updating all packages:**
The following command will check for updates for the installed packages.

```bash
 $ yum check-update
```

To download and install the updates run the following command.

```bash
 $ sudo yum update
```

7. **Clean the packages:**

```bash
 $ sudo yum clean packages
```

To clean the metadata of the packages

```bash
 $ sudo yum clean metadata
```

To clean the dbcache of the packages

```bash
 $ sudo yum clean dbcache
```

To rebuild the cache again use the following command.

```bash
 $ sudo yum makecache
```

8. **Install package from local file:**

It is also possible to install package from local file named package_name.rpm.

```bash
 $ sudo rpm -i package_name.rpm
```

9. **Check if a package is installed or not:**

To check if a package is installed or not use the following command.

```bash
 $ sudo rpm -qa | grep package_name
```

10. **Removing installed packages using RPM:**

```bash
 $ sudo rpm -e package_name
```

11. **Install package from source code:**

```bash
 $ tar zxvf sourcecode.tar.gz
 $ cd sourcecode
 $ ./configure
 $ make
 $ make install
```

**[⬆ Back to Top](#table-of-contents)**











