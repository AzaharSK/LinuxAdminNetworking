
### 1. Basic Search

```bash
$ grep "word" file.txt             # Search for a word in a file
$ grep -r "word" directory/        # Search in all files within a directory and its subdirectories Recursive
$ grep -i "word" file.txt          # Ignore Case- Perform a case-insensitive search
$ grep -n "word" file.txt          # Display the line number of each matching line
$ grep -w "word" file.txt          # Match only whole words (not substrings)
$ grep -c "word" file.txt          # Count the number of matching lines
$ grep -inr -E "error|warning" /path #  Search Multiple Patterns
$ grep -f patterns.txt file.txt      # Using -f to read patterns from a file
$ grep -l "word" *.txt               # Filter Files with Matches
$ cat file.txt | grep "word" | grep -v "exclude_this" 
```
### Log search
```bash
grep 'error' /var/log/syslog             # Search for the word 'error' in the syslog file
grep -i 'error' /var/log/syslog          # Case-insensitive search for 'error'
grep -r 'error' /var/log/                # Recursively search for 'error' in all files in /var/log/
dmesg | grep 'usb'                      # Filter output of dmesg to only show USB-related logs
```

### Using together
```bash
grep -inr "error" /var/log

Output:
/var/log/syslog:12:Error connecting to the server
/var/log/nginx/error.log:54:Error: file not found
```

### Invert Match
Show lines that do not match the pattern:
```bash
grep -v "word" file.txt
```
### Search Multiple Patterns
Match lines containing any of the patterns:
```bash
grep -E "pattern1 | pattern2" file.txt
```
* Use-case
```bash
grep -inr -E "error|warning" /path
```
Using -f to read patterns from a file:
```bash
grep -f patterns.txt file.txt
```

###  Filter Files with Matches
Display only the names of files containing matches:

```bash
grep -l "word" *.txt
```
Display files that do not contain matches:

```bash
grep -L "word" *.txt
```
### Match Beginning or End of Line
Match lines starting with a word:
```bash
grep "^word" file.txt
```
Match lines ending with a word:
```bash
grep "word$" file.txt
```
### Search Compressed Files
Search directly inside compressed files (e.g., .gz):
```bash
zgrep "word" file.gz
```
### Fixed String Search
Match the exact string, treating the pattern as a literal (no regex):
```bash
grep -F "word" file.txt
```
### Use Grep with Piping
Chain grep with other commands to refine output:
```bash
cat file.txt | grep "word" | grep -v "exclude_this"
```

### which - Shows the path of the executable file for a command.

```bash
user@Server# which python3
/usr/bin/python3

### whereis - Locates the binary, source, and manual page files for a command.

```bash
whereis ifconfig
```
This will show the location of the ifconfig executable, source, and man page files.
Note: It does not search user directories, only system directories like /usr/bin, /bin, /sbin, etc.

### locate -  Quickly finds files using a prebuilt database of file paths.
This will search for all paths containing index.html.
Note: If the file was created recently, it might not be in the database. Use the updatedb command to refresh the database.
```bash
sudo updatedb
locate index.html
```

### find

```bash
find / -type d -name conf       # Finds directories named "conf"
find / -user donc               # Finds all files owned by the user "donc"
find / -name donc               # Finds files named "donc"
find -name 'index.html'         # Finds 'index.html' in current directory and subdirectories
find / -name 'index.html'       # Finds 'index.html' starting from the root directory
find -name 'sshd*'              # Finds files starting with 'sshd'
find -name '*' -size +500k      # Finds files larger than 500 KB
```

### Use grep with find
Efficiently search for a specific term in files matching a pattern (e.g., *.txt). 

```bash
$ find . -type f -name "*.log" | xargs grep -inr "error"

./server.log:34:Error initializing the database
./app.log:78:Error: file not found
``

```bash
find . -type f -name "*.txt" | xargs grep -inr "search_term" || echo "No matches found"
```
Using find with xargs and grep is a powerful way to:

* Search for text in specific file types.
* Handle large directories and file lists.
* Ensure performance and flexibility.


### find command
The find command is a powerful tool for searching and processing files and directories in Linux/Unix systems. Below are various use cases and examples for find:

### Find files by size e.g- larger than 100 MB
```bash
find /path/to/search -size +100M

# +100M: Files larger than 100 MB.
# -100M: Files smaller than 100 MB
```
### Find Files by Type
* -type d: Directories.
* -type f: Files.
* -type l: Symbolic links.

```bash
find /path/to/search -type d
```
###  Find files modified by time i.e - in the last 7 days
```bash
find . -type f -mtime -7   # Find files modified with in the last 7 days
find . -type f -mtime +7   # Find files modified more than 7 days ago
find . -type f -mtime 7    # Find files modified exactly 7 days ago

```

### Xarg  - It takes output from another command (like find, ls, or cat) and passes it as arguments to another command.

```bash
find /tmp -name '*.log' | xargs rm                       # Delete all .log files in the /tmp directory
find . -name '*.txt' | xargs -I {} mv {} {}.bak          # Rename all .txt files to .bak files.

find . -name '*.txt' | xargs tar -czf archive.tar.gz     # Compress all .txt files in a directory into a single .tar.gz file
find . -type f -size +1M | xargs tar -czf large_files.tar.gz # Compress Files Larger Than 1MB
find . -name 'error*' | xargs tar -czf error_files.tar.gz    # Archive Files by Name

find /tmp -type f -empty | xargs rm                      #  Remove all empty files from the /tmp directory.
find . -name '*.txt' | xargs -I {} echo {} | wc -l       # Count Number of Files in a Directory
```
