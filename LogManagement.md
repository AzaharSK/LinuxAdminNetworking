* #### View system logs in real-time:

```bash
tail -f /var/log/syslog
tail -f /var/log/messages
```
* #### View specific logs:

```bash
cat /var/log/auth.log
cat /var/log/kern.log
```
* #### Search for a specific string in logs:

```bash
grep "error" /var/log/syslog
```
* #### Clear log files (use with caution):

bash

> /var/log/syslog

* ### Check system logs for any issues:

```bash
dmesg | less
```
