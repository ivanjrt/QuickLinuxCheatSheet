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

# Current IP
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

# Router Table
```
ip r
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

# Update Pi-Hole
```
pihole -up
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
