# Top 250 Mac Terminal Commands Cheat Sheet with Examples

## File and Directory Operations

1. `ls` - List directory contents
   Example: `ls -la` (List all files including hidden ones in long format)

2. `cd` - Change directory
   Example: `cd Documents` (Change to Documents directory)

3. `pwd` - Print working directory
   Example: `pwd` (Displays current directory path)

4. `mkdir` - Make directory
   Example: `mkdir new_folder` (Creates a new directory named "new_folder")

5. `rmdir` - Remove directory
   Example: `rmdir empty_folder` (Removes an empty directory)

6. `rm` - Remove files or directories
   Example: `rm -rf old_folder` (Recursively removes a directory and its contents)

7. `cp` - Copy files or directories
   Example: `cp file.txt backup/` (Copies file.txt to backup directory)

8. `mv` - Move or rename files or directories
   Example: `mv old_name.txt new_name.txt` (Renames a file)

9. `touch` - Create an empty file or update file timestamps
   Example: `touch newfile.txt` (Creates a new empty file)

10. `cat` - Concatenate and print files
    Example: `cat file1.txt file2.txt` (Displays contents of both files)

11. `more` - View file contents one screen at a time
    Example: `more longfile.txt` (Displays file content page by page)

12. `less` - View file contents with backward movement
    Example: `less longfile.txt` (More flexible than 'more' for viewing files)

13. `head` - Output the first part of files
    Example: `head -n 5 file.txt` (Displays first 5 lines of the file)

14. `tail` - Output the last part of files
    Example: `tail -f logfile.txt` (Continuously shows the end of a growing file)

15. `grep` - Search for patterns in files
    Example: `grep "error" logfile.txt` (Finds lines containing "error" in the file)

16. `find` - Search for files and directories
    Example: `find . -name "*.txt"` (Finds all .txt files in current directory and subdirectories)

17. `chmod` - Change file permissions
    Example: `chmod 755 script.sh` (Gives read, write, execute permissions to owner, and read & execute to others)

18. `chown` - Change file owner and group
    Example: `chown user:group file.txt` (Changes the owner and group of file.txt)

19. `ln` - Create links between files
    Example: `ln -s /path/to/file linkname` (Creates a symbolic link)

20. `ditto` - Copy files and directories
    Example: `ditto -V mydir mydir_backup` (Copies directory while preserving metadata)

## System Information and Management

21. `top` - Display and update sorted information about processes
    Example: `top` (Shows a real-time view of running processes)

22. `ps` - Report process status
    Example: `ps aux` (Displays all running processes)

23. `kill` - Terminate processes
    Example: `kill -9 1234` (Forcefully terminates process with ID 1234)

24. `killall` - Kill processes by name
    Example: `killall Firefox` (Terminates all processes named Firefox)

25. `df` - Report file system disk space usage
    Example: `df -h` (Shows disk usage in human-readable format)

26. `du` - Estimate file space usage
    Example: `du -sh *` (Shows sizes of all items in current directory)

27. `diskutil` - Disk utilities command
    Example: `diskutil list` (Lists all disks and partitions)

28. `system_profiler` - Report system hardware and software configuration
    Example: `system_profiler SPHardwareDataType` (Displays hardware info)

29. `sw_vers` - Print macOS operating system version information
    Example: `sw_vers` (Shows macOS version, build version, and product name)

30. `sysctl` - Get or set kernel state
    Example: `sysctl hw.memsize` (Displays total RAM)

## Networking

31. `ping` - Send ICMP ECHO_REQUEST packets to network hosts
    Example: `ping google.com` (Tests connectivity to google.com)

32. `netstat` - Show network status
    Example: `netstat -an` (Shows all network connections and listening ports)

33. `ifconfig` - Configure network interface parameters
    Example: `ifconfig en0` (Displays info about the en0 network interface)

34. `traceroute` - Print the route packets trace to network host
    Example: `traceroute google.com` (Shows the path to google.com)

35. `nslookup` - Query Internet name servers interactively
    Example: `nslookup google.com` (Looks up DNS info for google.com)

36. `dig` - DNS lookup utility
    Example: `dig google.com` (More detailed DNS info than nslookup)

37. `whois` - Internet domain name and network number directory service
    Example: `whois apple.com` (Displays registration info for apple.com)

38. `curl` - Transfer data from or to a server
    Example: `curl https://example.com` (Fetches the content of the URL)

39. `wget` - Retrieves files using HTTP, HTTPS and FTP
    Example: `wget https://example.com/file.zip` (Downloads file.zip)

40. `ssh` - OpenSSH SSH client (remote login program)
    Example: `ssh user@remotehost` (Connects to remotehost as user)

## Text Processing

41. `sed` - Stream editor for filtering and transforming text
    Example: `sed 's/old/new/g' file.txt` (Replaces all occurrences of 'old' with 'new')

42. `awk` - Pattern-directed scanning and processing language
    Example: `awk '{print $1}' file.txt` (Prints the first field of each line)

43. `cut` - Remove sections from each line of files
    Example: `cut -d',' -f1 file.csv` (Extracts the first column of a CSV file)

44. `sort` - Sort lines of text files
    Example: `sort file.txt` (Sorts lines alphabetically)

45. `uniq` - Report or omit repeated lines
    Example: `sort file.txt | uniq` (Removes duplicate lines after sorting)

## Compression and Archiving

46. `tar` - Tape archiver
    Example: `tar -cvzf archive.tar.gz folder/` (Creates a compressed archive)

47. `gzip` - Compress or expand files
    Example: `gzip file.txt` (Compresses file.txt to file.txt.gz)

48. `gunzip` - Expand compressed files
    Example: `gunzip file.txt.gz` (Decompresses file.txt.gz)

49. `zip` - Package and compress (archive) files
    Example: `zip archive.zip file1 file2` (Creates a zip archive)

50. `unzip` - List, test and extract compressed files in a ZIP archive
    Example: `unzip archive.zip` (Extracts files from archive.zip)

## Package Management

51. `brew` - The Homebrew package management system
    Example: `brew install wget` (Installs wget using Homebrew)

52. `port` - The MacPorts package management system
    Example: `sudo port install nginx` (Installs nginx using MacPorts)

## User Management

53. `whoami` - Print effective user ID
    Example: `whoami` (Displays current user name)

54. `id` - Print user and group information
    Example: `id` (Shows user and group IDs)

55. `users` - Print the user names of users currently logged in
    Example: `users` (Lists current logged in users)

56. `last` - Show listing of last logged in users
    Example: `last` (Displays recent login history)

57. `sudo` - Execute a command as another user (typically as superuser)
    Example: `sudo nano /etc/hosts` (Edits hosts file with superuser privileges)

## Process Management

58. `launchctl` - Interface to launchd
    Example: `launchctl list` (Lists all running agents/daemons)

59. `open` - Open files and directories
    Example: `open -a "TextEdit" file.txt` (Opens file.txt with TextEdit)

60. `pkill` - Kill processes by name
    Example: `pkill -9 Safari` (Forcefully terminates all Safari processes)

## Disk and File System

61. `hdiutil` - Manipulate disk images
    Example: `hdiutil attach image.dmg` (Mounts a disk image)

62. `fsck` - File system consistency check and interactive repair
    Example: `sudo fsck -fy /dev/disk0s2` (Checks and repairs the specified filesystem)

63. `mount` - Mount file systems
    Example: `mount -t apfs /dev/disk1s1 /Volumes/NewDisk` (Mounts an APFS volume)

64. `umount` - Unmount file systems
    Example: `umount /Volumes/DiskName` (Unmounts the specified volume)

## System Control

65. `shutdown` - Close down the system at a given time
    Example: `sudo shutdown -h now` (Shuts down the system immediately)

66. `reboot` - Reboot the system
    Example: `sudo reboot` (Reboots the system)

67. `sleep` - Put the Mac to sleep
    Example: `pmset sleepnow` (Puts the Mac to sleep immediately)

## Development and Programming

68. `xcode-select` - Manages active developer directory for Xcode
    Example: `xcode-select --install` (Installs Xcode command line tools)

69. `gcc` - GNU Compiler Collection
    Example: `gcc -o program program.c` (Compiles C program)

70. `make` - GNU make utility to maintain groups of programs
    Example: `make` (Builds the project according to the Makefile)

71. `git` - Version control system
    Example: `git clone https://github.com/user/repo.git` (Clones a Git repository)

72. `python` - Python language interpreter
    Example: `python script.py` (Runs a Python script)

73. `ruby` - Ruby language interpreter
    Example: `ruby script.rb` (Runs a Ruby script)

74. `node` - Node.js JavaScript runtime
    Example: `node script.js` (Runs a Node.js script)

## Shell Scripting

75. `echo` - Write arguments to the standard output
    Example: `echo "Hello, World!"` (Prints "Hello, World!" to the console)

76. `printf` - Format and print data
    Example: `printf "Name: %s\nAge: %d\n" "John" 30` (Prints formatted output)

77. `read` - Read a line from standard input
    Example: `read -p "Enter your name: " name` (Prompts for user input)

78. `if` - Conditionally perform a command
    Example: `if [ "$a" -eq "$b" ]; then echo "a equals b"; fi`

79. `for` - Expand words, and execute commands for each one
    Example: `for i in 1 2 3; do echo $i; done` (Loops through list)

80. `while` - Execute commands as long as a test succeeds
    Example: `while [ $count -lt 5 ]; do echo $count; count=$((count+1)); done`

81. `case` - Conditionally perform commands based on pattern matching
    Example: `case "$var" in pattern1) command1;; pattern2) command2;; esac`

82. `test` - Check file types and compare values
    Example: `test -f file.txt && echo "File exists"` (Checks if file exists)

## Environment Variables

83. `env` - Set environment and execute command, or print environment
    Example: `env` (Prints all environment variables)

84. `export` - Set export attribute for shell variables
    Example: `export PATH=$PATH:/new/path` (Adds a new directory to PATH)

85. `alias` - Define or display aliases
    Example: `alias ll='ls -la'` (Creates an alias for 'ls -la')

86. `unalias` - Remove alias definitions
    Example: `unalias ll` (Removes the 'll' alias)

## Security and Encryption

87. `ssh-keygen` - Authentication key generation, management and conversion
    Example: `ssh-keygen -t rsa` (Generates an RSA key pair)

88. `openssl` - OpenSSL command line tool
    Example: `openssl rand -base64 12` (Generates a random base64 string)

89. `security` - Administer Keychains, create keys, and more
    Example: `security find-generic-password -ga "Chrome"` (Finds Chrome passwords in Keychain)

## Date and Time

90. `date` - Display or set date and time
    Example: `date "+%Y-%m-%d %H:%M:%S"` (Displays current date and time in specified format)

91. `cal` - Displays a calendar
    Example: `cal` (Shows calendar for the current month)

## System Maintenance

92. `softwareupdate` - System software update tool
    Example: `softwareupdate -l` (Lists available software updates)

93. `defaults` - Access the Mac OS X user defaults system
    Example: `defaults write com.apple.finder AppleShowAllFiles TRUE` (Shows hidden files in Finder)

94. `tmutil` - Time Machine utility
    Example: `tmutil startbackup` (Starts a Time Machine backup)

95. `scutil` - Manage system configuration parameters
    Example: `scutil --get ComputerName` (Gets the computer's name)

96. `caffeinate` - Prevent the system from sleeping
    Example: `caffeinate -t 3600` (Prevents sleep for 1 hour)

## Networking (Advanced)

97. `networksetup` - Configuration tool for network settings in macOS
    Example: `networksetup -getairportnetwork en0` (Gets current WiFi network)

98. `ipconfig` - View and control IP configuration state
    Example: `ipconfig getifaddr en0` (Gets IP address of en0 interface)

99. `airport` - Utility for managing airport wireless interfaces
    Example: `airport -s` (Scans for available WiFi networks)

100. `route` - Manually manipulate the routing table
     Example: `netstat -nr` (Displays the routing table)

## Performance and Monitoring

101. `vm_stat` - Show Mach virtual memory statistics
     Example: `vm_stat 5` (Displays VM stats every 5 seconds)

102. `iostat` - Report I/O statistics
     Example: `iostat -w 1` (Shows I/O stats every second)

103. `yes` - Output a string repeatedly until killed
     Example: `yes > /dev/null &` (Generates CPU load for testing)

104. `time` - Time command execution
     Example: `time sleep 5` (Measures how long the sleep command takes)

## Audio and Video

105. `afplay` - Audio file playing tool
     Example: `afplay sound.mp3` (Plays an MP3 file)

106. `say` - Convert text to audible speech
     Example: `say "Hello, Mac"` (Mac speaks the text)

107. `ffmpeg` - Multimedia framework for handling audio and video
     Example: `ffmpeg -i input.mp4 output.avi` (Converts video format)

## Spotlight

108. `mdfind` - Finds files matching a given query
     Example: `mdfind -name "document.pdf"` (Searches for files named "document.pdf")

109. `mdls` - Lists metadata attributes for a specified file
     Example: `mdls image.jpg` (Displays metadata for image.jpg)

## Miscellaneous Utilities

110. `pbcopy` - Copy standard input to the clipboard
     Example: `echo "Hello" | pbcopy` (Copies "Hello" to the clipboard)

111. `pbpaste` - Paste contents of the clipboard to standard output
     Example: `pbpaste > file.txt` (Pastes clipboard contents to file.txt)

112. `open` - Open files and directories
     Example: `open -a Safari https://www.apple.com` (Opens Apple's website in Safari)

113. `screencapture` - Capture screen image to file or clipboard
     Example: `screencapture -c` (Captures the screen to the clipboard)

114. `sips` - Scriptable image processing system
     Example: `sips -z 300 300 image.jpg` (Resizes image to 300x300 pixels)

115. `plutil` - Property list utility
     Example: `plutil -convert xml1 file.plist` (Converts plist to XML format)

116. `xattr` - Display and manipulate extended attributes
     Example: `xattr -l file.txt` (Lists extended attributes of file.txt)

117. `qlmanage` - QuickLook server tool
     Example: `qlmanage -p file.pdf` (Previews a PDF file)

## Text Editing

118. `nano` - Simple text editor
     Example: `nano file.txt` (Opens file.txt in nano editor)

119. `vim` - Vi Improved, a programmer's text editor
     Example: `vim script.sh` (Opens script.sh in vim editor)

120. `emacs` - GNU project Emacs editor
     Example: `emacs document.txt` (Opens document.txt in emacs)

## File Information

121. `file` - Determine file type
     Example: `file unknown_file` (Displays the type of unknown_file)

122. `wc` - Print newline, word, and byte counts for each file
     Example: `wc -l file.txt` (Counts lines in file.txt)

123. `stat` - Display file or file system status
     Example: `stat file.txt` (Shows detailed file information)

124. `diff` - Compare files line by line
     Example: `diff file1.txt file2.txt` (Shows differences between two files)

## Process Management (Advanced)

125. `nice` - Execute a utility with an altered scheduling priority
     Example: `nice -n 10 long_process` (Runs long_process with lower priority)

126. `renice` - Alter priority of running processes
     Example: `renice -n 5 -p 1234` (Changes priority of process ID 1234)

127. `at` - Execute commands at a later time
     Example: `echo "say hello" | at now + 1 minute` (Schedules a command)

128. `crontab` - Maintain crontab files for individual users
     Example: `crontab -e` (Edits the current user's crontab file)

## System Logs

129. `log` - Access system wide log messages
     Example: `log show --last 1h` (Shows log messages from the last hour)

130. `syslog` - Apple System Log utility
     Example: `syslog -k Time ge -24h` (Shows syslog entries from last 24 hours)

131. `tail` - Display the last part of a file
     Example: `tail -f /var/log/system.log` (Continuously shows new log entries)

## Disk Utility (Advanced)

132. `dd` - Convert and copy a file
     Example: `dd if=/dev/zero of=file.img bs=1M count=10` (Creates a 10MB file)

133. `diskutil` - Disk management utility
     Example: `diskutil list` (Lists all disks and partitions)

134. `hdid` - Mount disk images
     Example: `hdid image.dmg` (Mounts a disk image)

## Network Utilities (Advanced)

135. `tcpdump` - Dump traffic on a network
     Example: `sudo tcpdump -i en0` (Captures packets on en0 interface)

136. `lsof` - List open files
     Example: `lsof -i :8080` (Lists processes using port 8080)

137. `nc` (netcat) - Arbitrary TCP and UDP connections and listens
     Example: `nc -l 1234` (Listens on port 1234)

138. `telnet` - User interface to the TELNET protocol
     Example: `telnet example.com 80` (Connects to example.com on port 80)

## Programming and Development (Advanced)

139. `lldb` - The LLDB debugger
     Example: `lldb ./myprogram` (Starts debugging myprogram)

140. `otool` - Object file displaying tool
     Example: `otool -L /bin/ls` (Shows shared libraries used by ls)

141. `nm` - Display name list (symbol table)
     Example: `nm /usr/lib/libSystem.B.dylib` (Lists symbols in a dynamic library)

142. `strip` - Remove symbols from object files
     Example: `strip myprogram` (Removes debugging symbols from myprogram)

## Version Control (Git)

143. `git init` - Create an empty Git repository or reinitialize an existing one
     Example: `git init` (Initializes a new Git repository)

144. `git clone` - Clone a repository into a new directory
     Example: `git clone https://github.com/user/repo.git` (Clones a repository)

145. `git add` - Add file contents to the index
     Example: `git add .` (Stages all changes in the current directory)

146. `git commit` - Record changes to the repository
     Example: `git commit -m "Initial commit"` (Commits staged changes)

147. `git push` - Update remote refs along with associated objects
     Example: `git push origin main` (Pushes commits to the main branch)

148. `git pull` - Fetch from and integrate with another repository or a local branch
     Example: `git pull origin main` (Pulls changes from the main branch)

149. `git branch` - List, create, or delete branches
     Example: `git branch new-feature` (Creates a new branch)

150. `git checkout` - Switch branches or restore working tree files
     Example: `git checkout -b new-feature` (Creates and switches to a new branch)

## Shell Customization

151. `chsh` - Change login shell
     Example: `chsh -s /bin/zsh` (Changes the login shell to zsh)

152. `source` - Execute commands from a file in the current shell
     Example: `source ~/.zshrc` (Reloads the zsh configuration)

## System Information (Advanced)

153. `system_profiler` - Report system configuration
     Example: `system_profiler SPHardwareDataType` (Displays hardware info)

154. `pmset` - Manipulate power management settings
     Example: `pmset -g` (Displays all power management settings)

155. `spctl` - Security assessment policy subsystem
     Example: `spctl --status` (Shows Gatekeeper status)

## Xcode and Development

156. `xcodebuild` - Build Xcode projects and workspaces
     Example: `xcodebuild -project MyApp.xcodeproj` (Builds an Xcode project)

157. `xcrun` - Run or locate development tools and properties
     Example: `xcrun simctl list devices` (Lists available iOS simulators)

## Homebrew (Package Management)

158. `brew update` - Fetch latest version of homebrew and formula
     Example: `brew update` (Updates Homebrew itself)

159. `brew upgrade` - Upgrade outdated, unpinned brews
     Example: `brew upgrade` (Upgrades all outdated packages)

160. `brew list` - List all installed formulae and casks
     Example: `brew list` (Lists all installed Homebrew packages)

161. `brew info` - Display information about formula
     Example: `brew info wget` (Shows information about the wget package)

## AppleScript

162. `osascript` - Execute AppleScript
     Example: `osascript -e 'tell app "Finder" to display dialog "Hello"'` (Shows a dialog)

## Keyboard and Input

163. `defaults write` - Modify defaults
     Example: `defaults write -g KeyRepeat -int 2` (Sets a faster key repeat rate)

## Printing

164. `lpr` - Print files
     Example: `lpr document.pdf` (Prints a PDF document)

165. `lpstat` - Print cups status information
     Example: `lpstat -p` (Lists available printers)

## Remote Access

166. `screen` - Screen manager with VT100/ANSI terminal emulation
     Example: `screen` (Starts a screen session)

167. `tmux` - Terminal multiplexer
     Example: `tmux` (Starts a new tmux session)

## Encryption and Security

168. `srm` - Securely remove files or directories
     Example: `srm -v private_file.txt` (Securely deletes a file)

169. `openssl` - OpenSSL command line tool
     Example: `openssl enc -aes-256-cbc -in file.txt -out file.enc` (Encrypts a file)

## Performance Tuning

170. `purge` - Force disk cache to be purged (flushed and emptied)
     Example: `sudo purge` (Clears disk cache)

171. `sync` - Force completion of pending disk writes (flush cache)
     Example: `sync` (Flushes file system buffers)

## Hardware Information

172. `ioreg` - Show I/O Kit registry
     Example: `ioreg -l | grep -i capacity` (Shows battery capacity info)

173. `system_profiler` - Reports system hardware and software configuration
     Example: `system_profiler SPUSBDataType` (Shows info about USB devices)

## Networking (More Advanced)

174. `networksetup` - Configuration tool for network settings
     Example: `networksetup -setairportpower en0 on` (Turns on Wi-Fi)

175. `scutil` - Manage system configuration parameters
     Example: `scutil --dns` (Shows DNS configuration)

## File System

176. `hdiutil` - Manipulate disk images
     Example: `hdiutil create -size 100m -volname "Test" -fs HFS+ -srcfolder /path/to/folder disk.dmg` (Creates a disk image)

177. `diskutil` - Modify, verify and repair local disks
     Example: `diskutil verifyVolume /` (Verifies the startup disk)

## System Management

178. `launchctl` - Interfaces with launchd
     Example: `launchctl list` (Lists all loaded launchd jobs)

179. `defaults` - Access user defaults
     Example: `defaults read com.apple.finder` (Reads Finder preferences)

180. `systemsetup` - Configuration tool for certain machine settings in System Preferences
     Example: `sudo systemsetup -getcomputersleep` (Gets sleep settings)

## Terminal Tricks

181. `say` - Convert text to audible speech
     Example: `say "Your Mac can talk"` (Makes your Mac speak)

182. `caffeinate` - Prevent the system from sleeping
     Example: `caffeinate -t 3600` (Keeps system awake for 1 hour)

183. `banner` - Print large banner-like output
     Example: `banner Hello` (Prints "Hello" in large text)

184. `units` - Unit conversion
     Example: `units "15 pounds" "kilograms"` (Converts 15 pounds to kilograms)

## Accessibility

185. `vo` - VoiceOver utility
     Example: `vo help` (Displays VoiceOver commands)

## Application Specific

186. `sqlite3` - Command-line interface for SQLite
     Example: `sqlite3 database.db` (Opens SQLite database)

187. `pig` - Grunt shell for Apache Pig
     Example: `pig -x local script.pig` (Runs a Pig script locally)

188. `R` - Start R programming environment
     Example: `R` (Starts R interactive shell)

## Document Conversion

189. `textutil` - Manipulate text files of various formats
     Example: `textutil -convert txt file.docx` (Converts .docx to .txt)

## Data Processing

190. `jq` - Command-line JSON processor
     Example: `cat data.json | jq '.name'` (Extracts 'name' field from JSON)

191. `awk` - Pattern-directed scanning and processing language
     Example: `awk '{print $1}' file.txt` (Prints first column of each line)

192. `sed` - Stream editor for filtering and transforming text
     Example: `sed 's/foo/bar/g' file.txt` (Replaces all 'foo' with 'bar')

## Permissions and Ownership

193. `chflags` - Change file flags
     Example: `chflags hidden file.txt` (Makes a file hidden)

194. `umask` - Set file mode creation mask
     Example: `umask 022` (Sets default permissions for new files)

## Process Communication

195. `kill` - Terminate or signal a process
     Example: `kill -9 1234` (Forcefully terminates process with ID 1234)

196. `killall` - Kill processes by name
     Example: `killall Safari` (Terminates all Safari processes)

## System Calls and Debugging

197. `dtruss` - Trace system calls and signals
     Example: `sudo dtruss ls` (Traces system calls made by ls command)

198. `sample` - Profile a process during a time interval
     Example: `sample Safari 10` (Samples Safari process for 10 seconds)

## File Comparison and Patching

199. `diff` - Compare files line by line
     Example: `diff file1.txt file2.txt` (Shows differences between files)

200. `patch` - Apply a diff file to an original
     Example: `patch < patchfile.diff` (Applies a patch to files)

## Archiving and Compression

201. `zip` - Package and compress (archive) files
     Example: `zip archive.zip file1 file2` (Creates a zip archive)

202. `unzip` - Extract compressed files in a ZIP archive
     Example: `unzip archive.zip` (Extracts files from a zip archive)

203. `tar` - Tape archiver
     Example: `tar -cvzf archive.tar.gz folder/` (Creates a compressed tar archive)

204. `gzip` - Compress or expand files
     Example: `gzip file.txt` (Compresses file.txt to file.txt.gz)

205. `gunzip` - Expand compressed files
     Example: `gunzip file.txt.gz` (Decompresses file.txt.gz)

## Remote File Transfer

206. `scp` - Secure copy (remote file copy program)
     Example: `scp file.txt user@remotehost:/path/to/destination/` (Copies file to remote host)

207. `rsync` - Remote (and local) file-copying tool
     Example: `rsync -avz /source/ /dest/` (Syncs files from source to destination)

## Text Processing and Analysis

208. `grep` - File pattern searcher
     Example: `grep "error" logfile.txt` (Finds lines containing "error" in logfile.txt)

209. `wc` - Word, line, character, and byte count
     Example: `wc -l file.txt` (Counts the number of lines in file.txt)

210. `sort` - Sort lines of text files
     Example: `sort names.txt` (Sorts lines in names.txt alphabetically)

211. `uniq` - Report or omit repeated lines
     Example: `sort names.txt | uniq` (Removes duplicate lines after sorting)

212. `tr` - Translate or delete characters
     Example: `echo "HELLO" | tr '[:upper:]' '[:lower:]'` (Converts text to lowercase)

213. `cut` - Remove sections from each line of files
     Example: `cut -d',' -f2 data.csv` (Extracts the second column from a CSV file)

214. `paste` - Merge lines of files
     Example: `paste file1.txt file2.txt` (Merges lines from two files side by side)

## System Monitoring and Diagnostics

215. `top` - Display and update sorted information about processes
     Example: `top` (Shows a dynamic real-time view of running processes)

216. `htop` - Interactive process viewer (may need to be installed)
     Example: `htop` (Provides an interactive interface for process management)

217. `fs_usage` - Report system calls and page faults related to filesystem activity
     Example: `sudo fs_usage -f filesystem` (Monitors filesystem-related system calls)

218. `sudo powermetrics` - Display power and thermal metrics of Apple silicon Macs
     Example: `sudo powermetrics` (Shows detailed power and performance metrics)

219. `vm_stat` - Show Mach virtual memory statistics
     Example: `vm_stat 5` (Displays VM statistics every 5 seconds)

220. `sysctl` - Get or set kernel state
     Example: `sysctl hw.memsize` (Shows the total RAM)

## Database Management

221. `sqlite3` - Command-line interface for SQLite
     Example: `sqlite3 mydatabase.db` (Opens an SQLite database)

222. `psql` - PostgreSQL interactive terminal (if PostgreSQL is installed)
     Example: `psql -d mydatabase` (Connects to a PostgreSQL database)

223. `mysql` - MySQL command-line tool (if MySQL is installed)
     Example: `mysql -u username -p database_name` (Connects to a MySQL database)

## Version Control (Additional Git Commands)

224. `git status` - Show the working tree status
     Example: `git status` (Displays the state of the working directory and staging area)

225. `git log` - Show commit logs
     Example: `git log --oneline` (Shows commit history in a compact format)

226. `git diff` - Show changes between commits, commit and working tree, etc
     Example: `git diff` (Shows unstaged changes)

227. `git stash` - Stash changes in a dirty working directory
     Example: `git stash` (Temporarily stores modified tracked files)

## Cloud Services

228. `aws` - AWS Command Line Interface (if installed)
     Example: `aws s3 ls` (Lists S3 buckets if AWS CLI is configured)

229. `gcloud` - Google Cloud SDK (if installed)
     Example: `gcloud compute instances list` (Lists Compute Engine instances)

230. `az` - Azure Command-Line Interface (if installed)
     Example: `az vm list` (Lists Azure virtual machines)

## Container Management

231. `docker` - Docker command-line interface (if installed)
     Example: `docker ps` (Lists running containers)

232. `kubectl` - Kubernetes command-line tool (if installed)
     Example: `kubectl get pods` (Lists Kubernetes pods)

## Programming Language Management

233. `python` - Python language interpreter
     Example: `python script.py` (Runs a Python script)

234. `pip` - Package installer for Python
     Example: `pip install numpy` (Installs the numpy package for Python)

235. `node` - Node.js JavaScript runtime
     Example: `node script.js` (Runs a Node.js script)

236. `npm` - Node Package Manager
     Example: `npm install express` (Installs the Express.js package)

237. `ruby` - Ruby language interpreter
     Example: `ruby script.rb` (Runs a Ruby script)

238. `gem` - Ruby package manager
     Example: `gem install rails` (Installs the Ruby on Rails framework)

## MacOS-Specific Utilities

239. `softwareupdate` - System software update tool
     Example: `softwareupdate -l` (Lists available software updates)

240. `airport` - Utility for managing airport wireless interfaces
     Example: `airport -s` (Scans for available Wi-Fi networks)

241. `pkgutil` - Query and manipulate installed packages
     Example: `pkgutil --pkgs` (Lists all installed packages)

242. `xattr` - Display and manipulate extended attributes
     Example: `xattr -l file.txt` (Lists extended attributes of file.txt)

243. `codesign` - Create and manipulate code signatures
     Example: `codesign -v myapp.app` (Verifies the code signature of an app)

244. `instruments` - Xcode performance analysis and testing tool
     Example: `instruments -s devices` (Lists available devices for testing)

245. `xcode-select` - Manages active developer directory for Xcode
     Example: `xcode-select --print-path` (Prints the path of the active Xcode)

## Miscellaneous Utilities

246. `cal` - Displays a calendar
     Example: `cal` (Shows calendar for the current month)

247. `bc` - An arbitrary precision calculator language
     Example: `echo "scale=2; 5/3" | bc` (Calculates 5 divided by 3 with 2 decimal places)

248. `od` - Octal, decimal, hex, ASCII dump
     Example: `od -c file.bin` (Displays binary file contents in various formats)

249. `units` - Unit conversion
     Example: `units "15 pounds" "kilograms"` (Converts 15 pounds to kilograms)

250. `say` - Convert text to audible speech
     Example: `say "Your Mac can talk"` (Makes your Mac speak the given text)

This concludes our comprehensive list of 250 useful terminal commands for macOS. Remember that some commands may require additional software to be installed, and others might need root privileges to execute. Always exercise caution when using powerful commands, especially those that modify system settings or delete files.
