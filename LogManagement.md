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
* #### Clear the contents of /var/log/syslog:

```bash
cp /var/log/syslog /var/log/syslog.backup
sudo truncate -s 0 /var/log/syslog   
```

* ### Check system logs for any issues:

```bash
dmesg | less
```
