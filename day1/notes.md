🧠 WHY LINUX FOR DEVOPS? (INTERVIEW GOLD)
90% of servers run Linux

DevOps engineers: 
-Deploy apps on Linux
-Debug issues on Linux
-Automate Linux systems
-Secure Linux servers

If you know Linux → You are employable


1️⃣ What is Linux?
Open-source Operating System.
-Used in servers, cloud, containers, Kubernetes
-Stable, secure, fast
-Popular Distros
-Ubuntu (BEST for beginners)
-Amazon Linux
-CentOS
-Debian
👉 For DevOps: Ubuntu + Amazon Linux


Linux File System Structure (IMPORTANT)
📁 Core Directories
Directory	Purpose
/	        Root of the entire file system
/home	    Home directories for normal users
/root	    Home directory for root (admin) user
/etc	    System-wide configuration files
/var	    Variable data (logs, cache, mail, spool)
/bin	    Essential user commands (ls, cp, mv)
/sbin	    System/admin commands (shutdown, iptables)
/usr	    User-installed applications & libraries
/tmp	    Temporary files (auto-deleted on reboot)
/opt	    Optional/third-party software
/boot	    Bootloader & kernel files
/dev	    Device files (disks, USB, etc.)
/proc	    Virtual files showing system processes
/sys	    Kernel & hardware information
/mnt	    Temporary mount point
/media	    Auto-mounted devices (USB, CD)
/lib	    Shared libraries for system commands
/run	    Runtime process data



 3️⃣ ESSENTIAL LINUX COMMANDS (MEMORIZE + PRACTICE)
 📂 Navigation
- pwd           # current directory
-ls             # list files
-ls -la         # detailed list
-cd folder      # move into folder
-cd ..          # go back

📄 File Operations
-touch file.txt           #create empty file
-mkdir folder             #create folder
-rm file.txt              #delete file
-rmdir folder             #delete folder
-cat file.txt             #read file
-less file.txt            #view large files
-more file.txt            #view large files
-head file.txt            #first few lines
-tail file.txt            #last few lines
-echo "text" >file.txt    #write to file
-echo "text" >>file.txt   #append to file
-nano file.txt            #edit file (use arrow keys, ctrl + x to exit)
-vi file.txt              #alternative editor
-cp a.txt b.txt           #copy file
-mv old.txt new.txt       #rename or move file
-rm -r folder             #delete folder recursively
-vim file.txt             #edit file with vim


👤 Permissions (CRITICAL)
-ls -l                        #list permissions
-chmod +x script.sh         #add execute permission
-chown user file.txt          #change ownership
-sudo chown user file.txt     #sudo required if not owner
-chmod u+x file.sh             #give yourself execute permission
-chmod g+w file.sh             #give your group write permission
-chmod o+rwx file.sh           #give others read/write/execute permission
-chmod 755 file.sh             #set all permissions at once (owner rwx, group rx, other rx)
-chmod 777 file.sh             #give everyone full access
-chmod 644 file.sh             #remove write permission from owner/group/others
-chmod 600 file.sh             #only allow owner to read/write
-chmod 400 file.sh             #only allow owner to read
-chmod 555 file.sh             #allow owner/group/others to execute only
-rw-r--r-- 1 ubuntu ubuntu 26 Sep 28 14:39 file.txt
| |     |      |       |       |
| |     |      |       |       └─ #owner's last modified date/time
| |     |      |       └───────── #owner's group name
| |     |      └───────────────── #size in bytes
| |     └──────────────────── #owner's username
| └────────────────────────── #number of links to this file
└──────────────────────────── #file/directory type and permissions


⚙️ Processes & System
-top        #show running processes
-pkill app  #stop process by name
-kill PID   #stop process by ID
-ip addr    #IP addresses
-ifconfig   #interface config
-route      #routing table
-iostat     #disk usage stats
-vmstat     #memory usage stats
-w          #who is logged in
-last       #recent logins
-history    #command history
-htop       #interactive task manager
-ps aux     #processes
-df -h      #disk usage
-free -m    #RAM usage
-uptime     #system uptime


🌐 Networking
-ping google.com                          #check internet connectivity
-ip a                                     #IP address info
-netstat -tulnp                           #network connections
-curl https://example.com                 #fetch web page
-wget https://example.com/file.zip        #download file
-dig example.com                          #DNS lookup
-traceroute google.com                    #trace route to server


4️⃣ USERS & ROOT
-whoami        #show current user
-sudo su       #switch to superuser
-exit          #exit sudo mode


