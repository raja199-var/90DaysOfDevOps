# Day 03 – Linux Commands Cheatsheet:

## 1. File System Commands-

- `pwd` — It Shows the current working directory.
- `ls` — Lists files and directories in the current directory.
- `ls -la` — Lists all files, including hidden files, with detailed information.
- `cd directory` — Changes the current working directory.
- `mkdir folder\_name` — Creates a new directory.
- `touch file\_name` — Creates a new empty file.
- `echo "How are you" > hello.txt` — It adds the content into hello.txt file overwriting the file contents.
- `echo "Hello how are you?" >> hello.txt:` — It appends the text into the file.
- `cat file\_name` — It prints the content of a file on terminal.
- `cp source destination` — It copies files or directories to another location.
- `mv source destination` — It moves or renames a file or directory.
- `rm file\_name` — It removes a file.
- `rm -r` — It recursively removes a directory and its contents.
- `head file\_name -n 5` — It displays the first 5 lines of the file from top of the file.
- `tail file\_name -n 5` — It displays the 5 lines of the file from the bottom of the file.
- `vim file\_name` — It opens a text editor within the terminal to create or edit the file.
- Type `i` for insert mode and press esc button to get out of the insert mode.
- Then `\:wq!` to save and exit the file. and `\:q!` for without saving any changes.
- `du -sh` — It displays the total disk usage of a directory in human-readable format.
- `df -h` — It shows available and used disk space in human-readable format.

---

## 2. Process Management Commands-

- `ps` — It shows information about currently running processes.
- `ps aux` — It shows detailed information about all running processes.
- `top` — It shows running processes and system resource usage.
- `kill` — It stops a running process.
- `kill -9` — It forcefully terminates a process when normal termination does not work.

---

## 3. Networking Troubleshooting Commands

- `ping host` — It is used to check whether server is reachable over a network.
- `ip addr` — It displays network interfaces and their IP addresses.
- `ip route` — It displays the system's routing table.
- `dig domain` — It queries DNS information for a domain.
- `curl URL` — It sends HTTP requests and is useful for testing APIs and web services.
