# Computername and other info
```
hostnamectl
```
# To chance computer name
```
hostnamectl set-hostname {name-here}
vi /etc/hosts #Replace the old name for the new one here
```

# Linux Installed OS version
```
lsb_release -a
```

# Name of the type of Drive(s) being used
``` 
dmesg| grep sd
```

# if Debian for how much space on HDD(s), even USB,  (on the for line will tel you the Mount Drive name)
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

# Create an Empty File
```
touch fileName
```

#Read a txt file
```
less file
```
#First 10 Lines
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

# Download a file
```
wget https://gdlp01.c-wss.com/gds/0/0300004730/02/eosrt3-eos1100d-im2-c-en.pdf
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
    1 Method 1: Via Line by Line:
    ```java
    ssh useradmin@10.10.10.10 'bash -s' <<'ENDSCRIPT'
    echo "Computer Name: "  $(hostname) > Downloads/filelist.txt
    echo " "
    ls                                 >> Downloads/filelist.txt
    echo "Today's Date: "  $(date)     >> Downloads/filelist.txt
    ENDSCRIPT
    ```
 ```   
    
    2 Method 2: Via a script written in local:
    ssh rosivan@10.10.10.117 'bash -s' < runner.sh
    ```
  




  
 
 
 
 


