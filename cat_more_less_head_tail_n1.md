### You can create a new file and input text interactively
```bash
cat > newfile.txt
# Ctrl+D to save and exit.
```
### Display Files Contents 
```bash
cat filename.txt
cat file1.txt file2.txt file3.txt  # concatenating contentes of files
```
### Redirects data

```bash
cat file1.txt > newfile.txt   # This command redirects the contents of file1.txt into newfile.txt. If newfile.txt exists, it will be overwritten.
cat file1.txt >> existingfile.txt  # This command redirects the contents of file1.txt  or Append to an existing file but does not overrite
```
