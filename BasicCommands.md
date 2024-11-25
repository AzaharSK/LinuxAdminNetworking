
* `cal:` current months calendar
* `cal 1999:` calendar for 1999
* `cal -3:` calendar (last month, current and next month)
* `cal -y:` all year calendar
* `ncal:` New Calendar

```bash
mistu@ubuntu:~$ cal
   November 2024      
Su Mo Tu We Th Fr Sa  
                1  2  
 3  4  5  6  7  8  9  
10 11 12 13 14 15 16  
17 18 19 20 21 22 23  
24 25 26 27 28 29 30  
                      
mistu@ubuntu:~$ ncal
    November 2024     
Su     3 10 17 24   
Mo     4 11 18 25   
Tu     5 12 19 26   
We     6 13 20 27   
Th     7 14 21 28   
Fr  1  8 15 22 29   
Sa  2  9 16 23 30
```

* `date:` current date

```bash
mistu@ubuntu:~$ date
Saturday 23 November 2024 11:40:57 AM IST
```
### TimeZones:
* UTC timezone
* IST timeZone
* GMT timeZone

```bash  
mistu@ubuntu:~$ date -u
Saturday 23 November 2024 06:11:00 AM UTC
```
* ```TZ="Time_Zone" date```
```bash
mistu@ubuntu:~$ TZ="UTC" date
Saturday 23 November 2024 06:12:57 AM UTC

$ TZ="America/New_York" date
Thu Nov 22 11:38:00 EST 2024

$ TZ="Asia/Tokyo" date
Thu Nov 22 16:38:00 JST 2024

$ TZ="Europe/London" date
Thu Nov 22 16:38:00 GMT 2024
```
### Where timezone saved :
```bash
mistu@ubuntu:~$ cat /etc/timezone
Asia/Kolkata

mistu@ubuntu:~$ cat /etc/localtime 
IST+0630
IST-5:30
```
### TimeControl settings

```bash
mistu@ubuntu:~$ timedatectl
               Local time: Sat 2024-11-23 11:54:48 IST
           Universal time: Sat 2024-11-23 06:24:48 UTC
                 RTC time: Sat 2024-11-23 06:24:48
                Time zone: Asia/Kolkata (IST, +0530)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no

#  Setting Timezone Permanently
mistu@ubuntu:~$ t sudo timedatectl set-timezone "America/New_York"
```

### Formatting the Output Using +FORMAT
* You can customize the output of the date command by using a format string, which consists of various placeholders.
* Common Format Specifiers:
* %Y: Year (4 digits)
* %m: Month (2 digits)
* %d: Day of the month (2 digits)
* %H: Hour (24-hour format)
* %M: Minute (2 digits)
* %S: Second (2 digits)
* %T: Time in HH:MM:SS format
* %A: Full weekday name (e.g., Monday)
* %B: Full month name (e.g., January)

```bash
mistu@ubuntu:~$ date +"%Y-%m-%d"
2024-11-23
mistu@ubuntu:~$ date +"%Y:%m:%d"
2024:11:23
mistu@ubuntu:~$ date +"%Y-%m-%d %H:%M:%S"
2024-11-23 12:04:16
mistu@ubuntu:~$ date +"%A, %B %d, %Y %T"
Saturday, November 23, 2024 12:05:32
```
### Creating a Log File with the Current Date and Time
```bash
mistu@ubuntu:~$ mkdir log && cd log
mistu@ubuntu:~/log$ touch "logfile_$(date +"%Y-%m-%d_%H-%M-%S").log"
mistu@ubuntu:~/log$ ls
logfile_2024-11-23_12-09-05.log
mistu@ubuntu:~/log$ echo "This is a log entry" >> "logfile_$(date +"%Y-%m-%d_%H-%M-%S").log"
mistu@ubuntu:~/log$ cat logfile_2024-11-23_12-09-43.log 
This is a log entry
```
### Pass Date int logfile
```bash
mistu@ubuntu:~/log$ echo "$(date +"%Y-%m-%d %T") - Log entry" >> "logfile_$(date +"%Y-%m-%d").log"
mistu@ubuntu:~/log$ cat logfile_2024-11-23.log 
2024-11-23 12:13:29 - Log entry
```
  
* `clear:` clear console text
* `exit:` exits de terminal

### Hostname 

```bash
$hostname 
node1.ibm.com 
```
* node1 => server name
* ibm.com => domain name

### Switch USER
```bash
$su - username1 
$su - root
```
* -  => Load the env of the user "root"
* root => argument: root user

### LogOut

```bash
#CTRL + D
#exit
#logout
```

### Environment variable:

```bash
mistu@ubuntu:~$ env
SHELL=/bin/bash
SESSION_MANAGER=local/ubuntu:@/tmp/.ICE-unix/4142,unix/ubuntu:/tmp/.ICE-unix/4142
QT_ACCESSIBILITY=1
COLORTERM=truecolor
XDG_CONFIG_DIRS=/etc/xdg/xdg-ubuntu:/etc/xdg
SSH_AGENT_LAUNCHER=gnome-keyring
XDG_MENU_PREFIX=gnome-
GNOME_DESKTOP_SESSION_ID=this-is-deprecated
LANGUAGE=en_IN:en
GNOME_SHELL_SESSION_MODE=ubuntu
SSH_AUTH_SOCK=/run/user/1000/keyring/ssh
XMODIFIERS=@im=ibus
DESKTOP_SESSION=ubuntu
GTK_MODULES=gail:atk-bridge
PWD=/home/mistu
LOGNAME=mistu
XDG_SESSION_DESKTOP=ubuntu
XDG_SESSION_TYPE=wayland
SYSTEMD_EXEC_PID=4170
XAUTHORITY=/run/user/1000/.mutter-Xwaylandauth.W4XVX2
HOME=/home/mistu
USERNAME=mistu
IM_CONFIG_PHASE=1
LANG=en_IN

XDG_CURRENT_DESKTOP=ubuntu:GNOME
VTE_VERSION=6800
WAYLAND_DISPLAY=wayland-0
GNOME_TERMINAL_SCREEN=/org/gnome/Terminal/screen/306a64a3_48f8_4aba_b956_38fb34b7fb25
GNOME_SETUP_DISPLAY=:1
LESSCLOSE=/usr/bin/lesspipe %s %s
XDG_SESSION_CLASS=user
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
USER=mistu
GNOME_TERMINAL_SERVICE=:1.205
DISPLAY=:0
SHLVL=1
QT_IM_MODULE=ibus
XDG_RUNTIME_DIR=/run/user/1000
XDG_DATA_DIRS=/usr/share/ubuntu:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop
PATH=/home/mistu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin
GDMSESSION=ubuntu
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
_=/usr/bin/env
```
