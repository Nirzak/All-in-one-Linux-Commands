# All Useful Linux Commands In One Place

This whole repository is created to track all the useful linux commands in one place. Created for my own use but you can also star this repository to keep a track on this.

### Table of Contents

---

| No. | Topic                                                                   |
| --- | ----------------------------------------------------------------------- |
| 1   | [**General Commands**](#General-commands)                               |
| 2   | [**File Management Commands**](#File-management-commands)               |
| 3   | [**Permission Commands**](#Permissions-based-commands)                  |
| 4   | [**Networking Commands**](#Networking-commands)                         |
| 5   | [**Package Installing Commands**](#installing-packages)                 |
| 6   | [**Memory Usage Commands**](#Memory-usage)                              |
| 7   | [**System and Hardware information**](#system-and-hardware-information) |
| 8   | [**Search Files**](#search-files)                                       |
| 9   | [**SSH**](#ssh)                                                         |

### General Commands

1. **w:** w displays information about currently logged in users and what each user is doing.

   ```bash
    $ w
    23:35:01 up  2:29,  1 user,  load average: 0.72, 1.07, 1.04
    USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
    root   :1       :1               21:04   ?xdm?  34:58   0.01s /usr/lib
   ```

2. **who** Shows information about currently logged in user.

   ```bash
    $ who
    root   :1           2021-11-01 21:04 (:1)
   ```

   Here, from left,
   root - Login Name of the User<br />
   :1 - User terminal<br />
   2021-11-01 21:04 - Date & Time of login<br />

3. **whoami:** Shows the system’s username

   ```bash
    $ whoami
    root
   ```

4. **id:** This command is used to find out user and group names and numeric ID's (UID or group ID) of the current user or any other user in the server.

   ```bash
    $ id
    uid=1000(root) gid=1000(root) groups=1000(root),4(adm),    24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),132(lxd),133(sambashare)
   ```

5. **groups:** This command is used to display all the groups for which the user belongs to.

   ```bash
    $ groups
    root adm cdrom sudo dip plugdev lpadmin lxd sambashare
   ```

6. **users:** Displays usernames of all users currently logged on the system.

   ```bash
    $ users
    root
   ```

7. **last:** Displays a list of all last logged in users. The list can be huge according to the number of user logins.

   ```bash
    $ last
    root   :1           :1               Mon Nov  1 21:04    gone - no  logout
    reboot   system boot  5.13.0-20-generi Mon Nov  1 15:06   still running
    root   :1           :1               Mon Nov  1 20:30 - crash  (-5:24)
    reboot   system boot  5.13.0-20-generi Mon Nov  1 20:30   still running
    root   :1           :1               Mon Nov  1 23:53 - down   (-3:24)
    reboot   system boot  5.13.0-20-generi Mon Nov  1 23:53 - 20:29  (-3:23)
    root   :1           :1               Sun Oct 31 23:31 - down   (01:56)
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

13. **alias:** Rename a long repitive command with a short name. For example you can make the command ls -la to any of your suitable name like below example. Then you can use that name to use the command.

```bash
 $ ls -la
 drwxr-xr-x 8 root root 4096 Nov  2 11:25 .
 drwxr-xr-x 4 root root 4096 Nov  2 10:58 ..
 -rw------- 1 root root  765 Nov  2 13:26 .bash_history
 -rw-r--r-- 1 root root  220 Apr 18  2019 .bash_logout
 -rw-r--r-- 1 root root 3564 Oct 27 16:56 .bashrc

 $ alias nr="ls -la"
 $ nr
 drwxr-xr-x 8 root root 4096 Nov  2 11:25 .
 drwxr-xr-x 4 root root 4096 Nov  2 10:58 ..
 -rw------- 1 root root  765 Nov  2 13:26 .bash_history
 -rw-r--r-- 1 root root  220 Apr 18  2019 .bash_logout
 -rw-r--r-- 1 root root 3564 Oct 27 16:56 .bashrc
```
To unalias type,
`unalias <your alias name>`

```bash
 $ unalias nr
```

14. **clear:** Clears the terminal

```bash
 $ clear
```

**[⬆ Back to Top](#table-of-contents)**
