# Computername and other info
```
hostnamectl
```
# To chance computer name
```
hostnamectl set-hostname {name-here}
vi /etc/hosts #Replace the old name for the new one here
```

# Computer Uptime
```
uptime
```

# CPU Info
```
lscpu
```

# Task Manager
```
apt install htop
htop
```

# List PCI Network Devices
```
lspci  
# Look between those lines for the NIC. vm = Intel Corporation 82xxxx
```

# Full System Info
```
sudo lshw
lsshow -html > systeminfo.html
```

# Start/Stop/Restart a Service
```
systemctl start service name
systemctl stop service name
systemctl restart service name
```

# Kill a Process
* Identify the process of the App  ``` top ``` </br>
* Find the PID: via TOP   </br>
![image](https://user-images.githubusercontent.com/44326428/165007947-d8dfcc01-ea5b-423f-8a8c-c54137854bdf.png)<br/>
then 
```
killall 9
``` 
where the next number is the PID, to close </br>
 </br> or  <br/>
 *  Find the PID: via ```ps -ef | grep appname ```  </br>
 * ![image](https://user-images.githubusercontent.com/44326428/165008506-35b03cdb-4bef-48b1-b100-8a084431e9a8.png)
```
kill 9
```
 </br> or  <br/>
 * If using GUI, then ``` xkill ``` then click over the app to close  </br>
 
 
# Mute Volume
```
amixer set Master muteclear
```

# Linux Installed OS version
```
lsb_release -a
```

# Overview Configuration
```
sudo -i
```

# Name of the type of Drive(s) being used
``` 
dmesg| grep sd
```
# Check to see for Mounted Drives
```
mount
```
to Reload Mounts
```
sudo mount -a
```
# if Debian for how much space on HDD(s), even USB,  (on the for line will tell you the Mount Drive name)
``` 
df -h --total 
```
or
```
df -h --total | grep total
```
or
```
df -h --total | sed '4!d
```
or a better view with JSON output
```
wget https://github.com/muesli/duf/releases/download/v0.6.0/duf_0.6.0_linux_amd64.deb
dpkg -i duf_0.6.0_linux_amd64.deb
duf
```

# last reboots
```
last reboot
```

# Dates
```
cal
```

or with current Time
```
date
```

# Whos is logged In
```
w
```
or current 
```
whoami
```

# Running Processes
```
ps
```


# Find Out how Memory Dets
```
vmstat -s
```
or
```
free -h
```

# CPU Being Used
```
cat /proc/cpuinfo
```

# Current 
```
hostname -I
```

# Interfaces Devices
```
ip link show
``` 
OR
```
nmcli device status
```
OR
```
/sbin/ifconfig -a
```

# DEB, check for Updates/Upgrades
```
sudo apt update && sudo apt upgrade -y
``` 
afterwards
```
sudo apt autoremove
```

# Check Version for Pi-Hole
```
pihole -v
```
# Display specific lines from a file
```
tail -3 /var/log/cups/access_log
```

# Display the User's Group
```
id
```

# Create a new user and his Home DIR
```
useradd -c "John Doe" -m john
```
# Delete the user
```
userdel john
```
#Add the User to a group
```
usermod -aG sales john
```

# Create a shortcut
```
ln -s /path/to/file linkname
```

# Locating files
```
apt install mlocate
locate file.txt
```

# Location Path
```
pstree
```

# Create an Empty File
```
touch fileName
```

#Read a txt file
```
less file
```

# History
```
history
```

# Rename file
```
mv fileA fileB
```

# Update Pi-Hole
```
pihole -up
```
# Router Table
```
ip r
```
# Internet Gateway
```
ip r | grep ^def

# SSH
```
ssh username@IpAddress
```
**yes** </br>
then type in the _password_ for the host </br>

Check for status </br>
```
sudo service ssh status
```

# Static IP Address
GUI Method
![image](https://user-images.githubusercontent.com/44326428/128663929-34a42601-7c0f-4e9e-b503-4558dc3bbf2f.png)

# Restart
```
systemctl reboot -i
```

# TracerRoute for Ubuntu
```RUBY
sudo apt install inetutils-traceroute
sudo apt install traceroute
```

# Ping for a count of 3
```
ping -c 3 google.com
```

# Show Programs using the network
```
netstat -nutlp
```

# Renew or Release IP
Deb
```
systemctl restart network.service
```
or RPMs
```
systemctl restart networking.service	
```

# Get an IP from a DNS
```
dig google.com
```


# Download a file
```
wget https://gdlp01.c-wss.com/gds/0/0300004730/02/eosrt3-eos1100d-im2-c-en.pdf
```
# File / Folder properties
```
ls -all file.txt
ls -lh file.txt
ls -all folder
```
<br/> 8 Permissions: r=Read ; w=Write ; x=Execute <br/>
 
# Find file which sizes are between 5-10MB
```
sudo  find / -size +5M -size -10M
```

# Find all files which are accessed N days back
```
find / -atime 2
```
# Find modifies files in the last N minutes
```
find / -mmin -1
```
# JSON Utility
```
sudo apt install jshon -y
echo '{"name": "Kesk","surname":"norem"}' | jshon
echo '{"name": "Kesk","surname":"norem"}' | jshon > file.json
```

# TAR (Compression) - _tar -czvf name_of_file_to_be.tar.gz_ then the actual file
```
tar -czvf eosManual.tar.gz eosrt3-eos1100d-im2-c-en.pdf
```
Multiple folders & Files
```
tar -czvf file.tar.gz /home/user1/ /home/user2/
```
you can also exclude a folder ie. 
```
tar -czvf archive.tar.gz /home/user1 --exclude=*.mp3
```
To Extract file in same directory
```
tar -xzvf eosManual.tar.gz
```
To Extract file in different directory
```
tar -xzvf eosManual.tar.gz -C folder2/
```

# ZIP a file
Prerequisites:
```
sudo apt install zip unzip
```
Name of the file that will be, then the actual filename, Example: </br>
```
zip eosrt3-eos1100d-im2-c-en.zip  eosrt3-eos1100d-im2-c-en.pdf
```
To Zip many Files & Folders
```
zip -r Manuals.zip eosrt3-eos1100d-im2-c-en.pdf folderWfiles
```
To Unzip
```
unzip Manuals.zip
```

# Send Files
```
scp file.pkg remote_username@10.10.0.2:/remote/directory
```

# Remove Folders  (for a single file don't use the '_rf_')
 ```
 rm -rf folderWfiles/
 ```
 
 
 # Creating a script
 ```
 nano Downloads/runner.sh
 ```
 
Content of a simple script: </br>
``` Java
#!/bin/bash
echo "Computer Name: "  $(hostname) > Downloads/filelist.txt
echo " "
ls                                 >> Downloads/filelist.txt
echo "Today's Date: "  $(date)     >> Downloads/filelist.txt
```

Making it Executable </br>
```
sudo chmod 774 Downloads/runner.sh
```
Execution: ```./Downloads/runner.sh```


 # Deploying a script (only works from another Linux)
 * Method 1: Via Line by Line:
    ```java
    ssh useradmin@10.10.10.10 'bash -s' <<'ENDSCRIPT'
    echo "Computer Name: "  $(hostname) > Downloads/filelist.txt
    echo " "
    ls                                 >> Downloads/filelist.txt
    echo "Today's Date: "  $(date)     >> Downloads/filelist.txt
    ENDSCRIPT
    ```
* Method 2: Via a script written in local:
    ```
    ssh useradmin@10.10.10.10 'bash -s' < runner.sh
    ```
    
# Maniuplating Text: 
quotes.txt 
```Javascript
The present is theirs; the future, for which I really worked, is mine.
Our virtues and our failings are inseparable, like force and matter. When they separate, man is no more.
The day science begins to study non-physical phenomena, it will make more progress in one decade than in all the previous centuries of its existence

-Nikola Tesla
```
Picking and Highlighting specific word(s): 
```
grep "virtues" quotes.txt
```
Picking and Highlighting specific word(s), while guessing char(s)
```
grep "virt[a-z][a-z]" quotes.txt
```
Replacing specific word(s)
```
sed -i 's/I really worked/I really did not worked/g' quotes.txt
```
Convert Lower Case
```
sed -e 's/\(.*\)/\L\1/' hello.txt > output.txt
```

Toast Notification
```
#!/bin/bash
sleep 10
notify-send "notify.sh" "Task complete successfully"
```
Text Styles
``` Java
#!/bin/bash
bold=$(tput bold)
underline=$(tput smul)
italic=$(tput sitm)
info=$(tput setaf 2)
error=$(tput setaf 160)
warn=$(tput setaf 214)
reset=$(tput sgr0)
echo "${info}INFO${reset}: This is an ${bold}info${reset} message"
echo "${error}ERROR${reset}: This is an ${underline}error${reset} message"
echo "${warn}WARN${reset}: This is a ${italic}warning${reset} message"
```

# Multitasking
``` Java
#!/bin/bash
function task1() {
    echo "Running task1..."
    sleep 5
}
function task2() {
    echo "Running task2..."
    sleep 5
}
task1 &
task2 &
wait
echo "All done!"
```

# For Loops
While Loop
``` javascript
#!/bin/bash
while true;
do
    # Frame #1
    printf "\r< Loading..." 
    sleep 0.5
    # Frame #2 
    printf "\r> Loading..." 
    sleep 0.5 
done
```

# Directory Folders Content

<p>

     ```Ruby
| Folder  | Content |
| ------------- | ------------- |
| /.                   | Root Directory for every directory. Read/Write Only unlesss Sudo access |
| /                    | Everything on your Linux system is located under the / directory |
| /bin -> /usr/bin     | Contains the essential user binaries (programs) that must be present when the system is mounted in single-user mode  |
| /boot                | The startup files and the kernel, vmlinuz. In some recent distributions also grub data. Grub is the GRand Unified Boot loader and is an attempt to  get rid of the many different boot-loaders we know today.  | 
|/dev                  | directory contains a number of special files that represent devices. These are not actual files as we know them, but they appear as files — for example, /dev/sda represents the first SATA drive in the system. If you wanted to partition it, you could start a partition editor and tell it to edit /dev/sda, /dev/random produces random numbers.|
| /etc                 | Most important system configuration files are in /etc, this directory contains data similar to those in the Control Panel in Windows  |
| /home                | Home directories of the common users.  |
| /lib -> /usr/lib     | The /lib directory contains libraries needed by the essential binaries in the /bin and /sbin folder. Libraries needed by the binaries in the /usr/bin folder are located in /usr/lib  |
| /lib64 -> /usr/lib64 | Directory containing 64-bit system libraries. |
| /media               |  contains subdirectories where removable media devices inserted into the computer are mounted  |
| /mnt                 |  Directory used for temporarily mounting remote filesystems and other media  |
| /opt                 |  contains subdirectories for optional software packages  |
| /proc                |  /proc directory similar to the /dev directory because it doesn’t contain standard files. It contains special files that represent system and process information    |
| /root                |  The root user's home directory.  |
| /run                 |  A runtime scratch directory (RAM-based).|
| /sbin -> /usr/sbin   |  The /sbin directory is similar to the /bin directory. It contains essential binaries that are generally intended to be run by the root user for system administration  |
| /selinux             |  If your Linux distribution uses SELinux for security (Fedora and Red Hat, for example), the /selinux directory contains special files used by SELinux. It’s similar to /proc. Ubuntu doesn’t use SELinux, so the presence of this folder on Ubuntu appears to be a bug  |
| /srv                 |  Contains “data for services provided by the system.” If you were using the Apache HTTP server to serve a website, you’d likely store your website’s files in a directory inside the /srv directory  |
| /sys                 |  Directory containing devices, kernel modules, filesystems, and other kernel component info  |
| /tmp                 |  	Temporary space for use by the system, cleaned upon reboot|
| /usr                 |  	Programs, libraries, documentation etc. for all user-related programs.|
| /var                 |  Variable data files are stored here. This can include things like log files, MySQL, and other database files, web server data files, email inboxes, and much more.  |
```
