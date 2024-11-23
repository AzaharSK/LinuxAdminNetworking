
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
  
* `clear:` clear console text
* `exit:` exits de terminal
