### Types of files in the Linux system. 
* Regular files
* Directories
* Character device files
* Block device files
* Loccal domain sockes
* Named pipes (FIFOs)
* Symbolic links


#### file command -Outputs file type information for file.txt

```bash
$ file client.py   # client.py: Python script, ASCII text executable
$ file script.sh   # script.sh: ASCII text
$ file /dev/tty0   # /dev/tty0: character special (4/0)
$ file /dev/mem    # /dev/mem: character special (1/1)
$ file /dev/ptp0   # /dev/ptp0: character special (246/0)
$ file /dev/shm    # /dev/shm: sticky, directory
$ file /dev/nvme0n1 #/dev/nvme0n1: block special (259/0)
$ $ file /proc/bus/pci/00/00.0 /proc/bus/pci/00/00.0: data

```

### stat command - Display detailed information about a file. (size, permissions, modified time, etc.)
```bash
$ stat script.sh 
  File: script.sh
  Size: 18        	Blocks: 8          IO Block: 4096   regular file
Device: fc02h/64514d	Inode: 54292323    Links: 1
Access: (0775/-rwxrwxr-x)  Uid: (1572982680/ azahask)   Gid: (2130182657/domainusers)
Access: 2024-12-13 13:58:53.274508740 +0530
Modify: 2024-12-13 13:58:37.035180038 +0530
Change: 2024-12-13 13:58:45.104342948 +0530
 Birth: 2024-12-13 13:58:37.035180038 +0530

$ stat /dev/tty0
  File: /dev/tty0
  Size: 0         	Blocks: 0          IO Block: 4096   character special file
Device: 5h/5d	Inode: 14          Links: 1     Device type: 4,0
Access: (0620/crw--w----)  Uid: (    0/    root)   Gid: (    5/     tty)
Access: 2024-12-13 10:46:47.165998840 +0530
Modify: 2024-12-13 10:47:02.000000000 +0530
Change: 2024-12-13 10:46:47.165998840 +0530
 Birth: 2024-12-13 10:46:28.518999999 +0530


$ stat /dev/mem
  File: /dev/mem
  Size: 0         	Blocks: 0          IO Block: 4096   character special file
Device: 5h/5d	Inode: 4           Links: 1     Device type: 1,1
Access: (0640/crw-r-----)  Uid: (    0/    root)   Gid: (   15/    kmem)
Access: 2024-12-13 10:46:47.150998841 +0530
Modify: 2024-12-13 10:46:47.150998841 +0530
Change: 2024-12-13 10:46:47.150998841 +0530
 Birth: 2024-12-13 10:46:28.518999999 +0530

```
### basename - Extract the filename from a path.
```bash
$ basename /lhome/azahask/azaharWorkspace/Learning/python-crud-app/script.sh 
script.sh
```
### dirname - Extract the directory path from a file path.
```bash
$ dirname /lhome/azahask/azaharWorkspace/Learning/python-crud-app/script.sh 
/lhome/azahask/azaharWorkspace/Learning/python-crud-app
```

###  du - Display disk usage of files and directories in in human-readable format

```bash

$ du -h /lhome/azahask/azaharWorkspace/Learning/
4.0K	/lhome/azahask/azaharWorkspace/Learning/linuxAdmin
12K	/lhome/azahask/azaharWorkspace/Learning/python-grpc/__pycache__
36K	/lhome/azahask/azaharWorkspace/Learning/python-grpc
24K	/lhome/azahask/azaharWorkspace/Learning/python-crud-app
68K	/lhome/azahask/azaharWorkspace/Learning/

$ du -sh /lhome/azahask/azaharWorkspace/Learning/
68K	/lhome/azahask/azaharWorkspace/Learning/

```

### df -Shows disk space usage in a human-readable format

```bash
$ df -h
Filesystem                               Size  Used Avail Use% Mounted on
tmpfs                                     13G  4.3M   13G   1% /run
efivarfs                                 246K  178K   64K  74% /sys/firmware/efi/efivars
/dev/mapper/ubuntu--vg-ubuntu--lv--root  931G   22G  862G   3% /
tmpfs                                     63G  352M   63G   1% /dev/shm
tmpfs                                    5.0M  4.0K  5.0M   1% /run/lock
/dev/nvme0n1p2                           2.9G  568M  2.2G  21% /boot
/dev/nvme0n1p1                           511M  5.0M  507M   1% /boot/efi
tmpfs                                     13G  156K   13G   1% /run/user/1572982680
```

* The root partition has significant free space (only 3% usage), which provides flexibility for future storage needs. /dev/mapper/ubuntu--vg-ubuntu--lv--root  ,  862GB free available.
* Boot and EFI partitions have low usage, typical for system files and firmware requirements.
* Temporary file systems (tmpfs) have sufficient capacity and are not heavily utilized. Used for runtime data storage (non-persistent) during system operation. & Used to store lock files to prevent simultaneous access to certain resources.
* Firmware variable storage (/sys/firmware/efi/efivars) has higher usage but is not a concern as it is a small, specialized partition.
