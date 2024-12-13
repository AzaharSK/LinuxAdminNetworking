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
sudo > /var/log/syslog
```

* #### Check system logs for any issues:

```bash
dmesg | less     # To view the kernel ring buffer logs
dmesg | grep -i error # dmesg for Hardware Issues

journalctl  -k   # For systemd logs related to kernel events
journalctl -xe  # Show logs from the system's journal (including errors)

```
* #### Perf for Performance Profiling
* perf is a powerful tool for performance analysis. It can help you track CPU usage, cache misses, and more.
```bash
perf stat ./your_program
```

### Redirect output to a file and display it at the same time 
```bash
 # Writes the output to the file output.txt and simultaneously displays it on the terminal.
$ ls -l | tee output.txt  
$ ls -l | tee -a output.txt  # Append to a file instead of overwriting:
```

### Standard Streams && redirection

![image](https://github.com/user-attachments/assets/6d709336-f0ca-40c8-aa29-26cbbb2f0ae8)

```bash
$ ls > output.txt                               # This redirects STDOUT (1>) to output.txt, but errors (STDERR) are still shown in the terminal.
$ ls /nonexistent_directory 2> error.txt        # This sends only errors to error.txt. The 2> tells the shell to redirect file descriptor 2 (STDERR) to error.txt.
$ ls /nonexistent_directory &> output.txt       # Redirect STDOUT and STDERR to the same file
$ command > /dev/null 2>&1                      # This discards all output (both STDOUT and STDERR) by redirecting them to /dev/null.
```

