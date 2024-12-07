
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

### Use grep ls

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
