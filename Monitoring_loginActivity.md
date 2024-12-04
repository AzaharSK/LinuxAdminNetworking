
![image](https://github.com/user-attachments/assets/b90bf7d2-2f78-4b9e-907d-8e4230d51ceb)

### who :  Which all users are login right now ?
```bash
ubuntu@tryit:~$ who
root     pts/1        2024-11-26 04:56
root     pts/3        2024-11-26 05:00
```
### w :  what are the logged in users doing now ? 
```
ubuntu@tryit:~$ w
05:24:46 up 35 min,  2 users,  load average: 0.00, 0.00, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
root     pts/1    -                04:56    1.00s  0.24s  0.01s w
root     pts/3    -                05:00   10:14   0.02s  0.02s bash -i

```
### whoami and id - myusername ?
```bash
ubuntu@tryit:~$ whoami
ubuntu

ubuntu@tryit:~$ id
uid=1000(ubuntu) gid=1000(ubuntu) groups=1000(ubuntu),27(sudo),998(incus-admin)

```
### hostname - My machine name ?
```bash
ubuntu@tryit:~$ hostname
tryit
```


### 1. Using Log Files
* a) ```/var/log/auth.log``` (Debian/Ubuntu) or ```/var/log/secure``` (RHEL/CentOS/Fedora)
These log files store authentication and login-related information.

### View recent login attempts:

```bash
sudo tail /var/log/auth.log      # Debian/Ubuntu
sudo tail /var/log/secure        # RHEL/CentOS
```
### Search for specific login attempts:

```bash
sudo grep 'session opened' /var/log/auth.log
sudo grep 'Failed password' /var/log/auth.log
```
* b) ```/var/log/wtmp``` and ```/var/log/btmp```
* ```wtmp``` logs all successful login records.
* ```btmp``` logs all failed login attempts.

### View successful logins:
```bash
$ last -F                # Reads data from the /var/log/wtmp 
$ last -iF               # Show IP Address of Remote Logins
$ last -a                # Show Information for TTY/Terminal Sessions
$ last -s yesterday -t today  # The `-s` (since) and `-t` (until) options allow us to display login entries within a specific time period.
```

### Investigate more
```bash

$ last -d  # Converts IP addresses to hostnames if reverse DNS resolution is possible.
user1    pts/0    myhost.example.com   Tue Dec  3 14:22 - 14:30 (00:08)
user2    pts/1    192.168.1.12        Tue Dec  3 13:00 - 13:50 (00:50)

$ last -x  # Show System Events (Reboots, Shutdowns, etc.) and which user made runlevel changes.
reboot   system boot  5.4.0-90-generic   Tue Dec  3 10:00 - 14:30 (04:30)
shutdown system down  5.4.0-90-generic   Mon Dec  2 22:00 - 10:00 (12:00)

```

### View failed login attempts:

```bash
$ sudo lastb             #  Reads data from the /var/log/btmp
$ last -x | grep reboot  #Look at system reboots to identify unexpected shutdowns:

```

