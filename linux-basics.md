## Linux Basics
<a href="linux">Back</a>

### Directory Navigation
```python
pwd # Displays the current working directory
cp # copies directories
mv # Moves or renames directories and files (removes the source directory)

cd # Changes directory specified
cd ../.. # Changes two levels up
cd / # Changes to root directory

ls # Displays the contents of a directory. Options include:
    -a # displays all directory contents, including hidden content
    -l # displays extended information, owner, modified date, size, and permissions
    -al # displays listing of all contents, including hidden content
    -R # displays the contents of a directory and subdirectories.
    -R /etc # displays contents of /etc directory and subdirectories
    -d # displays directories but not files
    -r # reverses the sort order
```

### Create, Copy, Move Directories
```python
mkdir # Creates a new directory
    -p # create all directories within the specified path when that path does not already exist
mkdir /home/Fred/work_files # creates a directory named work_files within the specified path
cp # Copies directories & leaves the source contents intact
    -r or -R # options to recursively copy subdirectories and files within the directory
    cp -r /temp /home/user # copies the entire /temp directory (with all of its files, subdirectories, and files in the subdirectories) to the /home/user directory
mv # Moves or renames directories (and files). Moving directories removes the source directory and places it in the destination
    -f # overwrites a directory that already exist in the destination directory without prompting
    -i # prompts before overwriting a directory in the destination directory
    -n # never overwrites files in the destination directory
    mv /temp/station ~/doc/ # moves station from the /temp directory to the ~/doc directory
    mv /current /previous # renames the directory current to previous
```

### Remove Directories
```python
rmdir # Deletes an empty directory
rm # Removes the directory and file information from the file system
    -i # prompts before removing
    -r # removes directories, subdirectories, and files within them
    -f # eliminates prompt for read-only files and avoids an exit code error if a file doesn't exist
    rm -rf /home/user/temp # deletes the temp directory with all its subdirectories and files without prompting
    rm -r /home/user/* # deletes all directories and files in the /home/user directory
```

### Files
```python
touch # If the file does not exist, creates a blank version of the file. If the file does exist, updates the file's modification and last accessed times
cp # Copies files - leaves the source file intact
    -f # overwrites files that already exist in the destination directory
    -i # prompts before overwriting a file in the destination directory
mv # Moves or renames files (and directories). Moving files erases the source file
    -f # overwrites files that already exist in the destination directory
    -i # prompts before overwriting a file in the destination directory
    -n # never overwrites files in the destination directory
rm # Removes a file or directory
# Note: The rm command deletes a file or directory's inode, but it does not actually delete its data. To permanently remove data, use the shred command.
    -f # option to delete with a prompt
```
### File Permissions
<img src="/assets/images/permissions.jpg" alt="Linux File Permissions">

### Working with Vi - Basics
The vi editor has two modes: Command and Insert. 

When you first open a file with vi, you are in Command mode. Command mode means that you can use keyboard keys to navigate, delete, copy, paste, and do a number of other tasks—except entering text.

Press i: To enter Insert mode, press i. In Insert mode, you can enter text, use the Enter key to go to a new line, use the arrow keys to navigate text, and use vi as a free-form text editor.

```python
vi # Starts vi. Type the command at the shell prompt
vi [filename] # Starts vi and immediately begins working on the named file
Insert key # Enters insert mode from command mode
    i # shortcut for insert mode from command mode
Insert key # Also toggles between the insert and replace modes while in edit mode
Esc key # Enters command mode from edit mode
Delete key # Deletes text
z # Exits without saving
: # Enters command line mode from command mode
w # Saves the current document
w [filename] # names and saves the file
w! [filename] # overwrites the file
q # Exits vi. This produces an error if the text was modified
q! # Exits vi without saving
wq # Saves the document and exits vi (exit also works)
ZZ # Saves the file and quits
```

Starting the Editor = vi filename or vi (starts in command mode)

Insert Mode = press i to enter insert mode (esc to exit)

Saving and Quit = ZZ save file and quit