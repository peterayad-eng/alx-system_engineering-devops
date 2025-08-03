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
1.	Replacing : with newlines
2.	Counting the number of resulting lines

### Script
```bash
#!/bin/bash
echo $PATH | tr ":" "\n" | wc -l
```

### Usage
```bash
chmod +x 3-paths
source ./3-paths
# Example output:
# 7
```

---

## Task 4: Global variables

**Filename:** `4-global_variables`
**Objective:** Lists all environment variables.

### Description
Prints all global (environment) variables available in the current shell session.
Uses the printenv command to display only exported variables.

### Script
```bash
#!/bin/bash
printenv | sort
```

### Usage
```bash
chmod +x 4-global_variables
source ./4-global_variables
# Example output:
# HOME=/root
# HOSTNAME=bedff1571be8
```

---

## Task 5: Local variables

**Filename:** `5-local_variables`
**Objective:** Lists all variables and functions currently available in the shell.

### Description
This script uses the set command to list all local variables, environment variables, and shell functions available in the current shell context.

### Script
```bash
#!/bin/bash
set
```

### Usage
```bash
chmod +x 5-local_variables
source ./5-local_variables
# Example output:
# BASH=/bin/bash
# BASH_VERSION='4.3.46(1)-release'
# COLUMNS=133
# HOME=/home/julien
# LANG=en_US.UTF-8
# PATH=/usr/local/bin:/usr/bin:/bin
```

---

## Task 6: Local variable

**Filename:** `6-create_local_variable`
**Objective:** Create a local variable in the current shell session that is not exported to child processes.

### Description
This script defines a local shell variable named BEST and assigns it the value School.

### Script
```bash
#!/bin/bash
BEST="School"
```

### Usage
```bash
chmod +x 6-create_local_variable
source ./6-create_local_variable
# Example output:
# $ echo $BEST
# School
```

---

## Task 7: Global variable

**Filename:** `7-create_global_variable`
**Objective:** Create a global (environment) variable that is accessible not only in the current shell but also by all child processes started from it.

### Description
This script creates a global variable named BEST and assigns it the value School.

### Script
```bash
#!/bin/bash
export BEST="School"
```

### Usage
```bash
chmod +x 7-create_global_variable
source ./7-create_global_variable
# Example output:
# $ echo $BEST
# School
```

---

## Task 8: Every Addition to True Knowledge is an Addition to Human Power

**Filename:** `8-true_knowledge`
**Objective:** Perform shell arithmetic by adding 128 to the value stored in the environment variable TRUEKNOWLEDGE and print the result.

### Description
This script reads the value of the environment variable TRUEKNOWLEDGE, Adds 128 to it using shell arithmetic, and prints the result.

### Script
```bash
#!/bin/bash
echo $((TRUEKNOWLEDGE + 128))
```

### Usage
```bash
chmod +x 8-true_knowledge
source ./8-true_knowledge
# Example output:
# $ export TRUEKNOWLEDGE=1209
# $ source ./8-true_knowledge
# 1337
```

---

## Task 9: Divide and Rule

**Filename:** `9-divide_and_rule`
**Objective:** Perform shell arithmetic division using values from two environment variables POWER and DIVIDE and print the result.

### Description
This script reads the values of environment variables POWER and DIVIDE, divides POWER by DIVIDE using shell arithmetic, and prints the result.

### Script
```bash
#!/bin/bash
echo $((POWER / DIVIDE))
```

### Usage
```bash
chmod +x 9-divide_and_rule
source ./9-divide_and_rule
# Example output:
# $ export POWER=42784
# $ export DIVIDE=32
# $ source ./9-divide_and_rule
# 1337
```

---

