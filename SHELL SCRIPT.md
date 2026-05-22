🟢 SHELL SCRIPT BASICS

| Syntax / Command     | Explanation                                   |
| -------------------- | --------------------------------------------- |
| `#!/bin/bash`        | Shebang line that defines script interpreter. |
| `bash script.sh`     | Executes a shell script.                      |
| `./script.sh`        | Runs script (needs execute permission).       |
| `chmod +x script.sh` | Gives execute permission to script.           |

🟡 VARIABLES

| Syntax               | Explanation                                  |
| -------------------- | -------------------------------------------- |
| `VAR=value`          | Declares a variable.                         |
| `echo $VAR`          | Prints variable value.                       |
| `readonly VAR=value` | Makes variable read-only.                    |
| `unset VAR`          | Removes variable.                            |
| `export VAR=value`   | Makes variable available to child processes. |


🔵 USER INPUT

| Syntax                        | Explanation                      |
| ----------------------------- | -------------------------------- |
| `read var`                    | Takes user input.                |
| `read -p "Enter name: " name` | Takes input with prompt message. |
| `read -s password`            | Takes hidden input (password).   |


🟣 CONDITIONAL STATEMENTS

| Syntax                     | Explanation                     |
| -------------------------- | ------------------------------- |
| `if [ condition ]; then`   | Starts if block.                |
| `elif [ condition ]; then` | Else-if condition.              |
| `else`                     | Executes if condition is false. |
| `fi`                       | Ends if block.                  |
| `[ $a -eq $b ]`            | Checks if equal.                |
| `[ $a -ne $b ]`            | Checks not equal.               |
| `[ $a -gt $b ]`            | Greater than.                   |
| `[ $a -lt $b ]`            | Less than.                      |
| `[ -f file ]`              | Checks if file exists.          |
| `[ -d dir ]`               | Checks if directory exists.     |


🟠 LOOPS

for i in 1 2 3
do
 echo $i
done

| Concept           | Explanation            |
| ----------------- | ---------------------- |
| `for var in list` | Iterates through list. |


While Loop

while [ condition ]
do
 command
done

| Concept           | Explanation                       |
| ----------------- | --------------------------------- |
| `while condition` | Executes while condition is true. |


Until Loop

until [ condition ]
do
 command
done

| Concept           | Explanation                        |
| ----------------- | ---------------------------------- |
| `until condition` | Runs until condition becomes true. |


🔴 CASE STATEMENT

case $var in
1) echo "One" ;;
2) echo "Two" ;;
*) echo "Default" ;;
esac

| Concept | Explanation                             |
| ------- | --------------------------------------- |
| `case`  | Multi-condition alternative to if-else. |


🟤 FUNCTIONS

myfunc() {
 echo "Hello"
}

| Syntax            | Explanation          |
| ----------------- | -------------------- |
| `function_name()` | Declares function.   |
| `return`          | Returns exit status. |
| `myfunc`          | Calls function.      |


🟡 POSITIONAL PARAMETERS

| Syntax  | Explanation                  |
| ------- | ---------------------------- |
| `$0`    | Script name.                 |
| `$1 $2` | First and second arguments.  |
| `$#`    | Number of arguments.         |
| `$@`    | All arguments.               |
| `$?`    | Exit status of last command. |
| `$$`    | Current process ID.          |

Example:

bash script.sh hello world

🔵 ARITHMETIC OPERATIONS

| Syntax         | Explanation             |
| -------------- | ----------------------- |
| `$((a+b))`     | Adds numbers.           |
| `expr $a + $b` | Arithmetic calculation. |
| `let a=a+1`    | Increments variable.    |

🟣 STRING OPERATIONS

| Syntax           | Explanation             |
| ---------------- | ----------------------- |
| `${#var}`        | Length of string.       |
| `${var:0:3}`     | Substring extraction.   |
| `${var/old/new}` | Replace text in string. |


🔥 FILE HANDLING & REDIRECTION

| Command    | Explanation                         |                                  |
| ---------- | ----------------------------------- | -------------------------------- |
| `>`        | Redirects output (overwrite).       |                                  |
| `>>`       | Appends output.                     |                                  |
| `<`        | Takes input from file.              |                                  |
| `2>`       | Redirects error output.             |                                  |
| `&>`       | Redirects both stdout & stderr.     |                                  |
| `          | `                                   | Pipes output to another command. |
| `tee file` | Writes output to file and terminal. |                                  |

🟢 COMMAND SUBSTITUTION

| Syntax          | Explanation                      |
| --------------- | -------------------------------- |
| `` `command` `` | Old method command substitution. |
| `$(command)`    | Modern command substitution.     |

Example:

DATE=$(date)

🟡 ARRAYS

| Syntax        | Explanation           |
| ------------- | --------------------- |
| `arr=(1 2 3)` | Declares array.       |
| `${arr[0]}`   | Access first element. |
| `${arr[@]}`   | All elements.         |
| `${#arr[@]}`  | Number of elements.   |

🔴 DEBUGGING & ERROR HANDLING

| Command                 | Explanation                  |
| ----------------------- | ---------------------------- |
| `set -x`                | Debug mode (shows commands). |
| `set +x`                | Turns off debug mode.        |
| `set -e`                | Exit script if error occurs. |
| `trap "command" SIGINT` | Handles signals.             |


🎯 DEVOPS REAL-TIME USAGE EXAMPLES

| Scenario              | Command                               |
| --------------------- | ------------------------------------- |
| Check service running | `systemctl status nginx`              |
| Restart service       | `systemctl restart nginx`             |
| Backup folder         | `tar -czvf backup.tar.gz folder/`     |
| Monitor logs          | `tail -f /var/log/messages`           |
| Auto cleanup script   | `find /tmp -type f -mtime +7 -delete` |
| Cron job              | `0 2 * * * /path/script.sh`           |








