#What is Linux?
Linux is a free and open-source, Unix-like operating system based on the Linux kernel. 
It manages hardware resources and provides an environment for running applications.I
It has different flavours like Ubuntu, RedHat, CentOS,Fedora etc. It can also be called as a kernel which is the heart of the operating system.


Linux Architecture:




What are the core components of Linux?
Kernel:This is the heart of the Linux which connects software with hardware. This has been written in C language.
Shell: This is a command line interface (CLI) which allows users to interact with the kernel by interpreting and translating into instructions that kernel can understand. E.g: bash, ssh, zsh,ksh,csh etc.
Applications: These are the software applications such as Developement tools, Web browsers, Database softwares etc.

Note: Everything in Linux is a process.
      It starts with PID(ProcessId) 1 i.e. systemd, where 'd' represents 'Daemon' (aka background process).



What systemd does and why it matters?

What does systemd do and why does it matter?
systemd is the system and service manager used by many modern Linux distributions. During boot, it usually runs as PID 1.
Its main responsibility is to start, stop, monitor, and manage system services and background processes so that the operating system runs properly and efficiently.
Before systemd, Linux commonly used older init systems such as SysVinit. These systems generally started services sequentially, which could make the boot process slower.
systemd can start multiple services in parallel when their dependencies allow it, which can improve boot time.
systemd can also monitor services. If a service crashes, it can automatically restart the service when it has been configured to do so.
We mainly use the systemctl command to interact with systemd.
With systemctl, we can start, stop, restart, enable, disable, and check the status of services.


Example: How does your laptop start?

                          POWER ON
                            ⬇️
  MOTHERBOARD - (BIOS) BASIC INPUT OUTPUT SYSTEM [BIOS AKA FIRMWARE]
                            ⬇️
          BOOTLOADER (lINUX KERNEL KA CODE KAHA RAKHA HAI)
                            ⬇️
                  KERNEL (STARTS A PROCESS)
                            ⬇️
                  SYSTEMD (PID) PROCESS ID 1
                            ⬇️
            DOCKER/KUBERNETES/SSH/NGINX/PRINTER/SCANNER

   

Processes:
A process is a running instance of a program. Every process has a unique PID and is managed by the Linux kernel.

Common Process States-
Running (R): Currently executing or ready to run on the CPU.

Sleeping (S): Waiting for an event or resource; normal for many processes.

Uninterruptible Sleep (D): Usually waiting for I/O; can indicate an I/O problem if persistent.

Stopped (T): Process execution has been paused.

Zombie (Z): Process has finished, but its parent has not yet collected its exit status.



File System Hierarchy:
'/' is a root directory (aka folder).
Everything in Linux starts from '/'.
Everything in Linux is a file or directory.
Everything in Linux is a process.


Shell commands for practice:
pwd: This shows present working directory.
ls: List files or directory. (d = directory, l = Link)
cd: This is used to change directory.
cat: It displays the content of a file.
touch : It is used to create file.



