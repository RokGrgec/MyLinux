# My Linux Commands and Reminders

## Some basic commands
- ```cd dirname``` - changing dir
- ```mkdir dirname``` - creating new directory
- ```rmdir dirname``` - removing directory
- ```rm -f filename``` - removing file
- ```rm -r dirname``` - removing directory even if its not empty
- ```mv file1 file2``` - moving file1 to file2
- ```thunar``` - opens file on the filepath
- ```cat filename``` - lists file content
- ``` grep "keyword" ``` - finds the word in given list, Example: ```cat filename | grep "keyword" ```
- ``` echo PATH``` - prints directories that contain executable files  
- ``` sudo dpkg -i /path/to/DownloadedFile.deb``` - updating aplications from .dep files
## Bash basics
- find
    Searches through everything
    Example: ```find / -name myfile```

- locate
    First use updatedb to build local database of all the files on the
    system, or nothing will be shown in screen
    Example: ```locate myfile```

- which
    Searches the folders in the $PATH variable
    Example: ```which nc```

- pwd (Print working directory)
    Example: pwd

- passwd (change current user password)
    example: passwd

- ls (list)
    example: ls -lah

- cat (echo file on screen)
    example: cat myfile

- echo (echo command parameter)
    Example: echo Hello > myfile

- grep (search for string inside another string)
    Example: cat myfile | grep something

- cut (extract columns of data)
    Example: cat myfile | cut –f 2 –d ":"

- tr (remove specific characters)
    Example: tr –d “x”

- sed (replace specific part of the string)
    Example: sed s/day/night/ oldfile >newfile 

It’s all about piping
- Using | to pass the output of one command as an input
to another
- Example: output contents of the file "myfile" search
for lines with string "user" in the file and show only
these lines, then show the lines without 001 and
save it to file hello
```cat myfile | grep user | grep –v 001 > hello```


## Linux basic troubleshooting commands

- ifconfig – identify and configure IP and MAC
    Example: ifconfig eth0 192.168.100.100/24

- ip – identify and configure IP and MAC
    Example: ip address

- arp – identify IP to MAC mappings
    Example: arp

- netstat - identify open ports and established connections
    Example: netstat -tupan

- route – show routing table
    Example: route

- traceroute – identify routers between nodes
    Example: traceroute

- smbclient – establish SMB connection
    example: smbclient -W DEMO.LAB -U Username //Computername/c\$
    \\\\Compuername\\sharename or //computername/sharename

- rpcclient – powerufull enumeration tool
    Example: rpcclient -u USERNAME IP

- service – start, stop, pause the service
    Example: service apache2 start

- systemctl – start, stop pause service
    Example: systemctlstart apache2

- update-rc.d – start service automatically after reboot
    Example: update-rc.d apache2 enable

- journalctl - system logs for troubleshooting
    Example: journalctl –f

## Basic Commands

- mount – mount unmount FS
    Example: mount /what /where
- fdisk – create partition
    Interactive
- mkfs - create filesystem
    Example: mkfs –t ext4 /dev/sda1
- du - disk usage
    Example: du /data
- df – disk usage
    Example: df -h

- ps - process list
    Example: ps -ef
- top – process CPU/memory usage
    Example: top

## Linux File Premission Basics

- d rwx rwx rwx
    d – folder, can also be:
    Simbolic link (l), setuid/setgid (s), sticky bit permissions (t)
    rwx - read write execute
    First rwx set – owner permissions
    Second rwx set – group permissions
    Third rwx set – all users (world) permissions

- rwx;
• 0 – non of the permissions turned on                  _ _ _
• 1 – execute permission turned on                      _ _ x
• 2 – write permission turned on                        _ w _
• 3 – write execute permission turned on                _ w x
• 4 – read permission turned on                         r _ _
• 5 – read and execute permissions turned on            r _ x
• 6 – read and write permissions turned on              r w _
• 7 – read, write and execute permission turned on      r w x