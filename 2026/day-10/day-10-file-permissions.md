# Day 10 Challenge – File Permissions & File Operations

## Files Created
- devops.txt
- notes.txt
- script.sh
- project/

## Permission Changes

### script.sh
Before: -rw-r--r--  
After: -rwxr-xr-x  

### devops.txt
Before: -rw-r--r--  
After: -r--r--r--  

### notes.txt
Permission: 640 (-rw-r-----)

### project/
Permission: 755 (drwxr-xr-x)

## Commands Used
touch devops.txt  
echo "This is my DevOps notes" > notes.txt  
vim script.sh  
chmod +x script.sh  
chmod a-w devops.txt  
chmod 640 notes.txt  
mkdir project  
chmod 755 project  

## What I Learned
1. Linux permissions control who can read, write, and execute files.
2. Execute permission is mandatory to run scripts.
3. chmod supports both symbolic and numeric modes.
