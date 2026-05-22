🟢 BASIC LINUX COMMANDS

| Command        | Explanation                          |
| -------------- | ------------------------------------ |
| `pwd`          | Shows the present working directory. |
| `ls`           | Lists files and directories.         |
| `ls -l`        | Shows detailed file information.     |
| `ls -a`        | Shows hidden files.                  |
| `cd dir`       | Changes directory.                   |
| `cd ..`        | Moves one directory back.            |
| `mkdir name`   | Creates a new directory.             |
| `rmdir name`   | Deletes an empty directory.          |
| `touch file`   | Creates an empty file.               |
| `cp src dest`  | Copies files or directories.         |
| `mv src dest`  | Moves or renames files.              |
| `rm file`      | Deletes a file.                      |
| `rm -r dir`    | Deletes a directory recursively.     |
| `rm -rf dir`   | Force deletes without confirmation.  |
| `clear`        | Clears the terminal screen.          |
| `history`      | Shows command history.               |
| `man command`  | Displays manual page of a command.   |
| `echo text`    | Prints text to terminal.             |
| `cat file`     | Displays file content.               |
| `less file`    | Views file content page by page.     |
| `head file`    | Shows first 10 lines of a file.      |
| `tail file`    | Shows last 10 lines of a file.       |
| `tail -f file` | Monitors file in real time.          |


🟡 FILE PERMISSIONS & OWNERSHIP

| Command            | Explanation               |
| ------------------ | ------------------------- |
| `chmod 777 file`   | Changes file permissions. |
| `chmod +x file`    | Adds execute permission.  |
| `chown user file`  | Changes file owner.       |
| `chgrp group file` | Changes file group.       |


🔵 USER MANAGEMENT

| Command         | Explanation            |
| --------------- | ---------------------- |
| `useradd name`  | Creates a new user.    |
| `passwd name`   | Sets user password.    |
| `usermod`       | Modifies user account. |
| `userdel name`  | Deletes a user.        |
| `groupadd name` | Creates a new group.   |
| `groupdel name` | Deletes a group.       |

🟣 PROCESS MANAGEMENT

| Command       | Explanation                     |
| ------------- | ------------------------------- |
| `ps`          | Shows running processes.        |
| `ps -ef`      | Shows detailed process list.    |
| `top`         | Displays live system processes. |
| `htop`        | Interactive process viewer.     |
| `kill PID`    | Terminates a process.           |
| `kill -9 PID` | Force kills a process.          |
| `bg`          | Runs process in background.     |
| `fg`          | Brings process to foreground.   |


🔴 DISK & MEMORY COMMANDS
| Command      | Explanation                                |
| ------------ | ------------------------------------------ |
| `df -h`      | Shows disk usage in human-readable format. |
| `du -sh dir` | Shows directory size.                      |
| `free -m`    | Shows memory usage in MB.                  |
| `uptime`     | Shows system running time.                 |
| `mount`      | Displays mounted filesystems.              |
| `umount`     | Unmounts a filesystem.                     |


🟤 NETWORK COMMANDS

| Command                   | Explanation                           |
| ------------------------- | ------------------------------------- |
| `ifconfig`                | Shows network interface details.      |
| `ip a`                    | Displays IP address information.      |
| `ping host`               | Checks network connectivity.          |
| `netstat -tulnp`          | Shows open ports.                     |
| `ss -tulnp`               | Displays socket statistics.           |
| `curl url`                | Sends HTTP request to a URL.          |
| `wget url`                | Downloads files from web.             |
| `scp file user@host:path` | Securely copies files to remote host. |
| `ssh user@ip`             | Connects to remote server securely.   |


🟠 PACKAGE MANAGEMENT
| Command           | Explanation                  |
| ----------------- | ---------------------------- |
| `apt update`      | Updates package list.        |
| `apt upgrade`     | Upgrades installed packages. |
| `apt install pkg` | Installs a package.          |
| `apt remove pkg`  | Removes a package.           |

RHEL / CentOS / Amazon Linux


| Command           | Explanation                 |
| ----------------- | --------------------------- |
| `yum install pkg` | Installs a package.         |
| `yum update`      | Updates system packages.    |
| `dnf install pkg` | Installs package using DNF. |

🟢 ADVANCED LINUX COMMANDS

| Command                    | Explanation                          |
| -------------------------- | ------------------------------------ |
| `grep "text" file`         | Searches for text in a file.         |
| `grep -r text dir`         | Searches recursively in directories. |
| `find / -name file`        | Finds files by name.                 |
| `locate file`              | Quickly finds file paths.            |
| `awk '{print $1}' file`    | Prints specific column from file.    |
| `sed 's/old/new/' file`    | Replaces text in file.               |
| `tar -cvf file.tar dir`    | Creates tar archive.                 |
| `tar -xvf file.tar`        | Extracts tar archive.                |
| `zip file.zip file`        | Creates zip file.                    |
| `unzip file.zip`           | Extracts zip file.                   |
| `crontab -e`               | Edits scheduled jobs.                |
| `systemctl start service`  | Starts a service.                    |
| `systemctl stop service`   | Stops a service.                     |
| `systemctl status service` | Checks service status.               |
| `journalctl -xe`           | Shows system logs.                   |


🎯 INTERVIEW QUICK QUESTIONS
| Question                                 | Answer                                                             |
| ---------------------------------------- | ------------------------------------------------------------------ |
| Difference between `rm -r` and `rm -rf`? | `-r` deletes recursively, `-rf` deletes forcefully without prompt. |
| How to check open ports?                 | `netstat -tulnp` or `ss -tulnp`                                    |
| How to check disk full issue?            | `df -h` and `du -sh *`                                             |
| How to stop a running process?           | `kill PID`                                                         |




