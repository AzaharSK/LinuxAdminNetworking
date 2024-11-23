
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
 
  
* `clear:` clear console text
* `exit:` exits de terminal
