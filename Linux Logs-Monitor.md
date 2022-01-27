> # _RjRaju_

# __Linux Logs & Monitoring__
---
## Linux Logs Path
```
ls -las /var/log
cat /var/log/auth.log # authentication attempts
cat /var/log/auth.log | grep -e "sshd"
cat /var/log/auth.log | grep -e "authentication failure"
```
## _logs_
```
cat /var/log/wtmp
man last
last -aiF
man lastb
lastb -adF
lastb -adF root # lastb -adF (user)
man lastlog
lastlog -u root # lastlog -u (user)
w
```
## _System-Monitoring_
```
man who
who
top
sudo apt install htop
htop
sudo apt install glances
man glances
glances
sudo apt install whowatch
man whowatch
whowatch
```