### You can create a new file and input text interactively
```bash
cat > newfile.txt
# Ctrl+D to save and exit.
cat >> myfile.txt   # append content to an existing file
```
### Display Files Contents 
```bash
cat filename.txt
cat -v filename.txt                      # This shows non-printable characters, such as control characters
cat -n filename.txt                      # Show Content of a File with Line Numbers
cat file1.txt file2.txt file3.txt        # concatenating contentes of files
cat file1.txt file2.txt > mergedfile.txt # Concatenate and Save Output into a New File
cat -s filename.txt                      # Remove Extra Blank Lines
cat /etc/passwd /etc/group  /etc/hosts > users-and-groups.txt
```
### Redirects data

```bash
cat file1.txt > newfile.txt             # This command redirects the contents of file1.txt into newfile.txt. If newfile.txt exists, it will be overwritten.
cat file1.txt >> existingfile.txt       # This command redirects the contents of file1.txt  or Append to an existing file but does not overrite
```
### head
```bash
head filename.txt                      # View the first 10 lines of a file
head -n 20 filename.txt                # View the first 20 lines of a file
head -c 50 filename.txt                # View the first 50 bytes of a file
head -n 5 file1.txt file2.txt          # View the first 5 lines of multiple files -Preview large log files to check for the log file format, metadata, or headers.
```
### tail 
```bash
tail filename.txt                      # View the last 10 lines of a file
tail -n 20 filename.txt                # View the last 20 lines of a file
tail -f /var/log/syslog                # Monitor a log file in real time (great for system logs
```

### more	- View files page-by-page, forward only	Read large files one page at a time.
The more command displays the contents of a file one screen at a time. Unlike head or tail, it allows you to scroll through a file.
```bash
more filename.txt         # View a file page by page
more file1.txt file2.txt  # View the contents of multiple files
ls -l | more              #View the output of another command page by page
```
### less	View files, scroll back and forth	Navigate large files, search keywords
```bash
less filename.txt        # View a file page by page
less filename.txt
/error                   # Search for a specific word in the file (search for 'error'):
less file1.txt file2.txt  # View the contents of multiple files
ls -l | less   # View the output of another command page by page
```
__Navigation__
* __Spacebar:__ Move to the next page.
* __Enter:__ Scroll line by line.
* __q:__ Quit.
* View large log files interactively and search within them using /search_term.
* It’s better than more because you can scroll up and down

