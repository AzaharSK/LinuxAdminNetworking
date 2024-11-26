
### 1. Basic Search
Search for a word in a file:
```bash
grep "word" file.txt
```
### 2. Recursive Search
Search in all files within a directory and its subdirectories:
```bash
grep -r "word" directory/
```
### 3. Ignore Case
Perform a case-insensitive search:
```bash
grep -i "word" file.txt
```
### 4. Show Line Numbers
Display the line number of each matching line:
```bash
grep -n "word" file.txt
```
### Using together
```bash
grep -inr "error" /var/log

Output:
/var/log/syslog:12:Error connecting to the server
/var/log/nginx/error.log:54:Error: file not found
```
### 5. Match Whole Words
Match only whole words (not substrings):
```bash
grep -w "word" file.txt
```
### 6. Invert Match
Show lines that do not match the pattern:
```bash
grep -v "word" file.txt
```
### 7. Search Multiple Patterns
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
### 8. Highlight Matches
Highlight matching patterns in the output:
```bash
grep --color=always "word" file.txt
```
### 9. Count Matches
Count the number of matching lines:
```bash
grep -c "word" file.txt
```
### 10. Filter Files with Matches
Display only the names of files containing matches:

```bash
grep -l "word" *.txt
```
Display files that do not contain matches:

```bash
grep -L "word" *.txt
```
### 11. Match Beginning or End of Line
Match lines starting with a word:
```bash
grep "^word" file.txt
```
Match lines ending with a word:
```bash
grep "word$" file.txt
```
### 12. Search Compressed Files
Search directly inside compressed files (e.g., .gz):
```bash
zgrep "word" file.gz
```
### 13. Fixed String Search
Match the exact string, treating the pattern as a literal (no regex):
```bash
grep -F "word" file.txt
```
### 14. Use Grep with Piping
Chain grep with other commands to refine output:
```bash
cat file.txt | grep "word" | grep -v "exclude_this"
```

### 15. Use grep ls

### 16. Use grep with find
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
  
