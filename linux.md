# Top 200 Linux Commands Cheat Sheet for x86_64 GNU/Linux

## File and Directory Operations
1. `ls` - List directory contents
2. `cd` - Change directory
3. `pwd` - Print working directory
4. `mkdir` - Make directory
5. `rmdir` - Remove directory
6. `rm` - Remove files or directories
7. `cp` - Copy files or directories
8. `mv` - Move or rename files or directories
9. `touch` - Create an empty file or update file timestamps
10. `cat` - Concatenate and print files
11. `more` - View file contents one screen at a time
12. `less` - View file contents with backward movement
13. `head` - Output the first part of files
14. `tail` - Output the last part of files
15. `grep` - Search for patterns in files
16. `find` - Search for files and directories
17. `chmod` - Change file permissions
18. `chown` - Change file owner and group
19. `chgrp` - Change group ownership
20. `ln` - Create links between files

## System Information and Management
21. `uname` - Print system information
22. `hostname` - Show or set the system's host name
23. `uptime` - Show how long the system has been running
24. `date` - Display or set the system date and time
25. `cal` - Display a calendar
26. `w` - Show who is logged on and what they are doing
27. `whoami` - Print effective user ID
28. `id` - Print user and group information
29. `last` - Show listing of last logged in users
30. `ps` - Report process status
31. `top` - Display Linux processes
32. `htop` - Interactive process viewer
33. `kill` - Send a signal to a process
34. `pkill` - Signal processes based on name and other attributes
35. `killall` - Kill processes by name
36. `reboot` - Reboot the system
37. `shutdown` - Shut down the system
38. `halt` - Stop the system
39. `systemctl` - Control the systemd system and service manager
40. `service` - Run a System V init script

## User Management
41. `useradd` - Create a new user
42. `userdel` - Delete a user account
43. `usermod` - Modify a user account
44. `passwd` - Change user password
45. `su` - Switch user
46. `sudo` - Execute a command as another user
47. `visudo` - Edit the sudoers file
48. `groups` - Print group memberships for a user
49. `gpasswd` - Administer the /etc/group file
50. `newgrp` - Log in to a new group

## Package Management (for Debian-based systems)
51. `apt-get` - APT package handling utility
52. `apt` - Command-line interface for package management
53. `dpkg` - Package manager for Debian
54. `aptitude` - High-level interface to the package manager
55. `snap` - Tool to interact with snaps

## Package Management (for Red Hat-based systems)
56. `yum` - Yellowdog Updater Modified package manager
57. `rpm` - RPM Package Manager
58. `dnf` - Dandified YUM package manager

## Networking
59. `ping` - Send ICMP ECHO_REQUEST to network hosts
60. `ifconfig` - Configure network interface parameters
61. `ip` - Show / manipulate routing, network devices, interfaces and tunnels
62. `netstat` - Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships
63. `ss` - Another utility to investigate sockets
64. `route` - Show / manipulate the IP routing table
65. `traceroute` - Print the route packets trace to network host
66. `nslookup` - Query Internet name servers interactively
67. `dig` - DNS lookup utility
68. `host` - DNS lookup utility
69. `hostname` - Show or set the system's host name
70. `iptables` - Administration tool for IPv4 packet filtering and NAT
71. `curl` - Transfer data from or to a server
72. `wget` - Non-interactive network downloader
73. `ssh` - OpenSSH SSH client (remote login program)
74. `scp` - Secure copy (remote file copy program)
75. `rsync` - A fast, versatile, remote (and local) file-copying tool

## Text Processing
76. `sed` - Stream editor for filtering and transforming text
77. `awk` - Pattern scanning and processing language
78. `cut` - Remove sections from each line of files
79. `paste` - Merge lines of files
80. `sort` - Sort lines of text files
81. `uniq` - Report or omit repeated lines
82. `wc` - Print newline, word, and byte counts for each file
83. `tr` - Translate or delete characters
84. `diff` - Compare files line by line
85. `patch` - Apply a diff file to an original
86. `aspell` - Interactive spell checker

## File Compression and Archiving
87. `tar` - Tape archiver
88. `gzip` - Compress or expand files
89. `gunzip` - Expand compressed files
90. `bzip2` - A block-sorting file compressor
91. `bunzip2` - Decompress files
92. `xz` - Compress or decompress .xz and .lzma files
93. `unxz` - Decompress .xz files
94. `zip` - Package and compress (archive) files
95. `unzip` - List, test and extract compressed files in a ZIP archive

## Disk and File System Management
96. `df` - Report file system disk space usage
97. `du` - Estimate file space usage
98. `fdisk` - Manipulate disk partition table
99. `mkfs` - Build a Linux file system
100. `fsck` - Check and repair a Linux file system
101. `mount` - Mount a file system
102. `umount` - Unmount file systems
103. `dd` - Convert and copy a file
104. `parted` - A partition manipulation program
105. `lsblk` - List block devices

## System Monitoring and Performance
106. `free` - Display amount of free and used memory in the system
107. `vmstat` - Report virtual memory statistics
108. `iostat` - Report CPU statistics and input/output statistics for devices and partitions
109. `mpstat` - Report processors related statistics
110. `sar` - Collect, report, or save system activity information
111. `nmon` - Performance monitoring tool for Linux

## Process Management
112. `nice` - Run a program with modified scheduling priority
113. `renice` - Alter priority of running processes
114. `nohup` - Run a command immune to hangups
115. `watch` - Execute a program periodically, showing output fullscreen
116. `screen` - Screen manager with VT100/ANSI terminal emulation
117. `tmux` - Terminal multiplexer

## Scheduling
118. `at` - Queue, examine or delete jobs for later execution
119. `atq` - List the user's pending jobs
120. `atrm` - Delete jobs queued by at or batch
121. `crontab` - Maintain crontab files for individual users

## User Environment
122. `env` - Run a program in a modified environment
123. `printenv` - Print all or part of environment
124. `set` - Set or unset options and positional parameters
125. `export` - Set the export attribute for variables
126. `alias` - Define or display aliases
127. `unalias` - Remove alias definitions
128. `history` - GNU History Library
129. `echo` - Display a line of text
130. `printf` - Format and print data

## Shell Scripting
131. `test` - Check file types and compare values
132. `expr` - Evaluate expressions
133. `true` - Do nothing, successfully
134. `false` - Do nothing, unsuccessfully
135. `sleep` - Delay for a specified amount of time
136. `wait` - Wait for process to change state
137. `read` - Read from a file descriptor
138. `getopts` - Parse option arguments

## Security and Access Control
139. `chroot` - Run command or interactive shell with special root directory
140. `ulimit` - Get and set user limits
141. `getfacl` - Get file access control lists
142. `setfacl` - Set file access control lists
143. `chage` - Change user password expiry information
144. `fail2ban-client` - Fail2ban client command line interface

## Hardware Information
145. `lshw` - List hardware
146. `lscpu` - Display information about the CPU architecture
147. `lspci` - List all PCI devices
148. `lsusb` - List USB devices
149. `lsblk` - List block devices
150. `dmidecode` - DMI table decoder

## System Logs
151. `journalctl` - Query the systemd journal
152. `dmesg` - Print or control the kernel ring buffer
153. `lastlog` - Reports the most recent login of all users or of a given user
154. `zcat` - Compress or expand files
155. `zless` - File perusal filter for crt viewing of compressed text

## Miscellaneous
156. `bc` - An arbitrary precision calculator language
157. `xargs` - Build and execute command lines from standard input
158. `time` - Run programs and summarize system resource usage
159. `tee` - Read from standard input and write to standard output and files
160. `script` - Make typescript of terminal session
161. `strace` - Trace system calls and signals
162. `ltrace` - A library call tracer
163. `yes` - Output a string repeatedly until killed
164. `seq` - Print a sequence of numbers
165. `md5sum` - Compute and check MD5 message digest
166. `sha1sum` - Compute and check SHA1 message digest
167. `sha256sum` - Compute and check SHA256 message digest
168. `shred` - Overwrite a file to hide its contents, and optionally delete it
169. `strings` - Print the sequences of printable characters in files
170. `xxd` - Make a hexdump or do the reverse

## Programming and Development
171. `gcc` - GNU Compiler Collection
172. `make` - GNU make utility to maintain groups of programs
173. `gdb` - The GNU Debugger
174. `valgrind` - A suite of tools for debugging and profiling
175. `git` - The stupid content tracker (version control system)
176. `svn` - Subversion command line client tool
177. `ld` - The GNU linker
178. `nm` - List symbols from object files
179. `ar` - Create, modify, and extract from archives
180. `strip` - Discard symbols from object files

## X Window System
181. `startx` - Initialize an X session
182. `xauth` - X authority file utility
183. `xhost` - Server access control program for X
184. `xrandr` - Primitive command line interface to RandR extension
185. `xinput` - Utility to configure and test X input devices

## Audio
186. `alsamixer` - Graphical mixer program for ALSA soundcard driver
187. `amixer` - Command-line mixer for ALSA soundcard driver
188. `aplay` - Command-line sound player for ALSA soundcard driver
189. `arecord` - Command-line sound recorder for ALSA soundcard driver

## Power Management
190. `poweroff` - Power off the system
191. `suspend` - Suspend the system
192. `hibernate` - Hibernate the system
193. `pm-suspend` - Suspend the system using the pm-utils package
194. `pm-hibernate` - Hibernate the system using the pm-utils package

## System Information (Advanced)
195. `lsmod` - Show the status of modules in the Linux Kernel
196. `modinfo` - Show information about a Linux Kernel module
197. `modprobe` - Add and remove modules from the Linux Kernel
198. `uname` - Print system information
199. `dconf` - Low-level configuration system for GSettings
200. `update-alternatives` - Maintain symbolic links determining default commands

This cheat sheet provides a comprehensive list of essential Linux commands for x86_64 GNU/Linux systems. Remember that some commands may require root privileges to execute, and their availability can vary depending on your specific distribution and installed packages.
