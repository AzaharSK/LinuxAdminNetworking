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

```
### Redirects data

```bash
cat file1.txt > newfile.txt             # This command redirects the contents of file1.txt into newfile.txt. If newfile.txt exists, it will be overwritten.
cat file1.txt >> existingfile.txt       # This command redirects the contents of file1.txt  or Append to an existing file but does not overrite
```
