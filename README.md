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
| 8   | [**System**](#system)                                                   |

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
    uid=1000(nirjas) gid=1000(nirjas) groups=1000(nirjas),4(adm),    24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),132(lxd),133(sambashare)
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

13. **alias:** Rename a long repitive command with a short name. For example you can make the command ls -la to any of your suitable name like below example. Then you can use that name to use the command.

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

14. **clear:** Clears the terminal

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
3. **ls**: The ls command is used to list directories and files. 

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

2. **mkdir** The mkdir (make directory) command allows users to create directories or folders.

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

3. **rmdir**: The rmdir (remove directories) is used to remove empty directories. To delete directories that contains files and fodlers refer to `rm -r directoryName`.

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

4. **rm**: The rm (remove) command is used to remove files, directories, symbolic links etc from the file system.
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

5. **touch**: The touch command is used to create new empty files. Touch is also used to change timestamps on existing files and directories. 
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
6. **cat**: The cat command is used to view contents of single or multiple files, concatenate files and redirect output in terminal or files.

   ```bash
    $ cat file1 file2
   ```

7. **file**: The file command is used to know the file type.

   ```bash
    $ file file1.txt
    file1.txt: ASCII text
   ```

8. **less**: If a file content is very large then less can be used to view the file contents as a paged manner.

   ```bash
    $ less largefile.txt
   ```
Use the following command to navigate through less: <br />
 q - Used to quit out of less and go back to your shell.<br />
 Page up, Page down, Up and Down - Navigate using the arrow keys and page keys.<br/>
 g - Moves to beginning of the text file.<br />
 G - Moves to the end of the text file. <br />
 /search - You can search for specific text inside the text document. Prefacing the words you want to search with / <br />
 h - If you need a little help about how to use less while you’re in less, use help.

**[⬆ Back to Top](#table-of-contents)**
