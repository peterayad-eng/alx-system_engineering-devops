# 0x03-shell_variables_expansions

## Task 0: Alias

**Filename:** `0-alias`  
**Objective:** Create a script that defines an alias in the shell.

### Description
This script creates an alias for the `ls` command so that it will run `rm *` instead.  
This means that typing `ls` after running the script will **delete all files** in the current directory instead of listing them.

### Script
```bash
#!/bin/bash
alias ls='rm *'

