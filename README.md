# Computername and other info
```
hostnamectl
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

# SSH
```
ssh username@IpAddress
```
**yes** </br>
then type in the _password_ for the host </br>

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

# Download a file
```
wget http://domain.com/archive
```


