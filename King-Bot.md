
> # __Rj Raju__

# __King-Bot__

# This is My TryHackMe Cheat Sheet

# While [ Loop ]
```bash
while [ 1 ]; do chattr -i /root/king.txt 2>/dev/nulll; echo RjRaju > /root/king.txt;  chattr +i /root/king.txt 2>/dev/null; done
```

# Find Flag
```bash
find 2>/dev/null | while read line; do busybox strings $line | grep -oE "[0-9a-f]{32}" ;done

find -name "*flag*" | while read line; do strings $line; do | grep thm

find / -type f -name flag* -exec cat {} \; 2>/dev/null

find / -type f -name flag* 2>/dev/null

grep -rnw . -e 'thm{[0-9,a-z]*}'

grep -RoE "thm\{.*"

find -name "*flag*.txt"
```

# python $6$
```python
import crypt
crypt.crupt("raju")
```

# Hijack pts sessions
```bash
script /dev/pts/2
```

# pts sessions spam
```bash
cat < /dev/pts/2
mesg n
w
```

# get the proccess ID of the pty .
```bash
ps -t pts/2
```

# script
```bash
#!/bin/bash
US=$(tty | cut -c 6-)

w | grep -v "$US" | grep -v "115" | grep pts | awk '{print $2}' | while read line; do
    cat /dev/null > /dev/$line &
done
```

# Stabilize shell
```bash
/usr/bin/script -qc /bin/bash /dev/null
```

# Fun
```bash
apt install terminal-parrot
apt install nyancat
apt install cmatrix
apt install sl
```

# End-Game

:(){ :|: & };:
