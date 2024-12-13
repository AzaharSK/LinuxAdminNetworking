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
