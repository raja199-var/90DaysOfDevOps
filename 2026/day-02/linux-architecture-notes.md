# Linux

## What is Linux?

Linux is a free and open-source, Unix-like operating system based on the Linux kernel.

It manages hardware resources and provides an environment for running applications.

Linux has different flavours (distributions), such as:

- Ubuntu
- Red Hat
- CentOS
- Fedora

The **Linux kernel** is the core component or "heart" of the operating system. It connects software with hardware and manages system resources.

---

## Linux Architecture

```text
+---------------------------+
|       Applications        |
+---------------------------+
|           Shell           |
+---------------------------+
|          Kernel           |
+---------------------------+
|          Hardware         |
+---------------------------+
```

---

## What are the Core Components of Linux?

Linux mainly consists of the following core components:

### 1. Kernel

The **Kernel** is the heart of Linux. It connects software with hardware and manages system resources.

The kernel manages:

- CPU
- Memory
- Processes
- Devices
- Networking
- File systems

The Linux kernel is primarily written in **C language**.

---

### 2. Shell

The **Shell** is a Command Line Interface (CLI) that allows users to interact with the operating system.

It interprets user commands and translates them into instructions that the kernel can understand.

Examples of shells:

- Bash
- Zsh
- Ksh
- Csh

> **Note:** SSH is not a shell. SSH is a protocol/tool used to securely connect to a remote Linux machine.

---

### 3. Applications

Applications are software programs that run on top of the operating system.

Examples:

- Development tools
- Web browsers
- Database software
- Text editors
- Docker
- Monitoring tools

---

## Processes in Linux

A **process** is a running instance of a program.

Every process has a unique **PID (Process ID)** and is managed by the Linux kernel.

On modern Linux systems using `systemd`, the first userspace process normally runs with:

```text
PID 1 → systemd
```

Here, `d` represents **daemon**, which generally refers to a background service or process.

> **Note:** Everything in Linux is not literally a process. Linux manages many different resources, including processes, files, devices, sockets, and more.

---

## What Does systemd Do and Why Does It Matter?

`systemd` is the system and service manager used by many modern Linux distributions.

During boot, it usually runs as **PID 1**.

Its main responsibilities include:

- Starting services
- Stopping services
- Restarting services
- Monitoring services
- Managing background processes
- Managing service dependencies

This helps the operating system run properly and efficiently.

---

## systemd vs SysVinit

Before `systemd`, Linux commonly used older initialization systems such as **SysVinit**.

SysVinit generally started services sequentially, which could make the boot process slower.

`systemd` can start multiple services in parallel when their dependencies allow it, which can improve boot time.

It can also monitor services and automatically restart a service if it crashes, when configured to do so.

---

## systemctl

We mainly use the `systemctl` command to interact with `systemd`.

### Common systemctl Commands

```bash
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
systemctl status nginx
systemctl enable nginx
systemctl disable nginx
```

### What Do These Commands Do?

| Command | Purpose |
|---|---|
| `systemctl start nginx` | Starts the Nginx service |
| `systemctl stop nginx` | Stops the Nginx service |
| `systemctl restart nginx` | Restarts the Nginx service |
| `systemctl status nginx` | Checks the status of Nginx |
| `systemctl enable nginx` | Enables Nginx to start automatically during boot |
| `systemctl disable nginx` | Disables automatic startup of Nginx during boot |

---

## How Does Your Laptop Start?

A simplified Linux boot process looks like this:

```text
                    POWER ON
                       ↓
             +-------------------+
             | Motherboard       |
             | BIOS / UEFI       |
             | Firmware          |
             +-------------------+
                       ↓
                  Bootloader
                    (GRUB)
                       ↓
                    Kernel
                       ↓
                systemd (PID 1)
                       ↓
             Start System Services
                       ↓
        +--------------+--------------+
        ↓              ↓              ↓
       SSH           Docker         Nginx
        ↓              ↓              ↓
     Services      Containers      Web Server
```

### Boot Process Explained

#### 1. Power On

The computer is powered on.

#### 2. BIOS / UEFI

The firmware initializes the hardware and starts the boot process.

#### 3. Bootloader

The bootloader loads the Linux kernel into memory.

A common Linux bootloader is **GRUB**.

#### 4. Kernel

The Linux kernel initializes hardware and starts the first userspace process.

#### 5. systemd

On systems using `systemd`, it normally runs as:

```text
PID 1 → systemd
```

It starts and manages system services.

#### 6. Services and Applications

Services such as SSH, Docker, Nginx, printing services, and other applications can start based on their configuration and dependencies.

---

## Processes

A **process** is a running instance of a program.

Every process has:

- A unique PID
- A process state
- A parent process
- Allocated memory
- Resources managed by the Linux kernel

You can view running processes using:

```bash
ps
```

or:

```bash
ps aux
```

You can also use:

```bash
top
```

or:

```bash
htop
```

to monitor processes.

---

## Common Process States

Linux processes can have different states.

| State | Meaning |
|---|---|
| `R` - Running | Currently executing or ready to run on the CPU |
| `S` - Sleeping | Waiting for an event or resource; normal for many processes |
| `D` - Uninterruptible Sleep | Usually waiting for I/O |
| `T` - Stopped | Process execution has been paused |
| `Z` - Zombie | Process has finished, but its parent has not yet collected its exit status |

### Running (R)

The process is currently executing or is ready to run on the CPU.

### Sleeping (S)

The process is waiting for an event or resource. This is normal for many processes.

### Uninterruptible Sleep (D)

The process is usually waiting for I/O.

If a process remains in the `D` state for a long time, it may indicate an underlying I/O problem.

### Stopped (T)

The execution of the process has been paused.

### Zombie (Z)

The process has finished execution, but its parent process has not yet collected its exit status.

---

## File System Hierarchy

The Linux filesystem starts from the root directory:

```text
/
```

The `/` is called the **root directory**.

Unlike Windows, Linux does not use drive letters such as `C:` or `D:` as the starting point of the filesystem.

A simplified Linux filesystem looks like:

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── opt
├── proc
├── root
├── tmp
├── usr
└── var
```

### Important Points

- `/` is the root directory.
- Everything in the Linux filesystem starts from `/`.
- Linux represents many system resources through files or file-like interfaces.
- Processes are managed by the Linux kernel.

---

## Important Linux Directories

| Directory | Purpose |
|---|---|
| `/` | Root directory |
| `/home` | User home directories |
| `/root` | Home directory of the root user |
| `/etc` | Configuration files |
| `/var` | Variable data such as logs |
| `/tmp` | Temporary files |
| `/boot` | Boot-related files |
| `/dev` | Device files |
| `/proc` | Process and kernel information |
| `/usr` | User-space programs and libraries |
| `/opt` | Optional/add-on software |

---

## Shell Commands for Practice

### 1. `pwd`

`pwd` stands for **Present Working Directory**.

It shows the current working directory.

```bash
pwd
```

Example:

```text
/home/raja
```

---

### 2. `ls`

`ls` is used to list files and directories.

```bash
ls
```

Useful options:

```bash
ls -l
ls -a
ls -la
```

In `ls -l` output:

- `d` → Directory
- `l` → Symbolic link
- `-` → Regular file

---

### 3. `cd`

`cd` is used to change the current directory.

```bash
cd /home
```

Go to the parent directory:

```bash
cd ..
```

Go to the home directory:

```bash
cd ~
```

---

### 4. `cat`

`cat` is used to display the contents of a file.

```bash
cat filename.txt
```

Example:

```bash
cat notes.txt
```

---

### 5. `touch`

`touch` is used to create an empty file.

```bash
touch notes.txt
```

Example:

```bash
touch linux-notes.txt
```

---

## Quick Summary

| Topic | Key Point |
|---|---|
| Linux | Free and open-source Unix-like operating system |
| Kernel | Core of the operating system |
| Shell | Interface for interacting with the operating system |
| Applications | Software that runs on the operating system |
| Process | Running instance of a program |
| PID | Unique Process ID |
| systemd | System and service manager |
| PID 1 | Usually `systemd` on modern Linux systems |
| `/` | Root directory |
| `pwd` | Shows current directory |
| `ls` | Lists files and directories |
| `cd` | Changes directory |
| `cat` | Displays file contents |
| `touch` | Creates an empty file |
| `systemctl` | Used to manage systemd services |

---

## Key Takeaways

- Linux is a free and open-source operating system.
- The **kernel** is the core of Linux.
- The **shell** allows users to interact with the operating system through commands.
- A **process** is a running instance of a program.
- Every process has a unique **PID**.
- On modern Linux systems using `systemd`, **systemd normally runs as PID 1**.
- `systemctl` is commonly used to manage services.
- The Linux filesystem starts from the **root directory `/`**.
- Commands such as `pwd`, `ls`, `cd`, `cat`, and `touch` are basic Linux commands.
