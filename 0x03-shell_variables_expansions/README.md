# 0x03-shell_variables_expansions

This project covers Shell initialization files, variables, expansions, shell arithmetic, aliases, and command execution.

---

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
```

### Usage
```bash
chmod +x 0-alias
source ./0-alias
ls      # Deletes all files in current directory
\ls     # Lists files normally (bypasses alias)
```

---

## Task 1: Hello you

**Filename:** `1-hello_you`
**Objective:** Print hello user, where user is the current Linux user.

### Description
This script uses the $USER environment variable to display a personalized greeting.

### Script
```bash
#!/bin/bash
echo "hello $USER"
```

### Usage
```bash
chmod +x 1-hello_you
source ./1-hello_you
# Example output:
# hello root
```

---

## Task 2: The path to success is to take massive, determined action

**Filename:** `2-path`
**Objective:** Add /action to the end of the system PATH variable.

### Description
This script modifies the PATH environment variable so that /action is the last directory the shell checks when searching for commands.

### Script
```bash
#!/bin/bash
export PATH=$PATH:/action
```

### Usage
```bash
chmod +x 2-path
source ./2-path
echo $PATH
# Output example:
# /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/action
```

---

## Task 3: If the path be beautiful, let us not ask where it leads

**Filename:** `3-paths`
**Objective:** Count the number of directories in the PATH.

### Description
This script counts how many directories are in the system's PATH variable by:
1. Replacing : with newlines
2. Counting the number of resulting lines

### Script
```bash
#!/bin/bash
echo $PATH | tr ':' '\n' | wc -l
```

### Usage
```bash
chmod +x 3-paths
source ./3-paths
# Example output:
# 7
```

---

