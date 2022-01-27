# My custom alias & functions

> __Rj Raju__

# My-alias
```bash
alias vpn="sudo openvpn vpnfile.ovpn"
alias vpnip='ifconfig tun0 | grep netmask | cut -b 9- | cut -d" " -f2'
alias myip='ifconfig eth0 | grep netmask | cut -b 9- | cut -d" " -f2'
alias dockip='ifconfig docker0 | grep netmask | cut -b 9- | cut -d" " -f2'
alias cls="clear"
alias root="sudo su"
```

# My-Functions

```bash
fullupdate(){
        clear
        echo ""
        echo "Update Starting ..."
        echo ""
        sleep 3
        sudo apt-get update
        sudo apt-get upgrade -y
        sudo apt-get dist-upgrade -y
        sudo apt-get autoremove -y
        echo ""
        echo "Update Completed :)"
        echo ""
        return
}
fullupdate
```
-  __output :__
```

Update Starting ...

Get:1 http://ftp.harukasan.org/kali kali-rolling InRelease [30.6 kB]
Get:2 http://ftp.harukasan.org/kali kali-rolling/main i386 Packages [17.7 MB]
12% [2 Packages 1,308 kB/17.7 MB 7%]                                    194 kB/s 10min 9s
.
.
.
```
---
```bash
server(){
        echo "vpnip : \c";ifconfig tun0 | grep netmask | cut -b 9- | cut -d" " -f2
        pwd
        echo "Listening on port 80"
        python3 -m http.server 80
        return
}
server
```
-  __output :__
```

vpnip : 721.0.1.5
/home/linux/Desktop
Listening on port 80
Serving HTTP on 0.0.0.0 port 80 (http://0.0.0.0:80/) ...

```
---
```bash
lserver(){
        echo "myip : \c";ifconfig eth0 | grep netmask | cut -b 9- | cut -d" " -f2
        pwd
        echo "Listening on port 80"
        python -m SimpleHTTPServer 80
        return
}
lserver
```
-  __output :__
```

myip : 10.10.10.11
/home/linux/Desktop
Listening on port 80
Serving HTTP on 0.0.0.0 port 80 ...

```
---
```bash
allip(){
        echo ""
        echo "MyIp     : \c "
        ifconfig eth0 | grep netmask | cut -b 9- | cut -d" " -f2
        echo "vpnIP    : \c "
        ifconfig tun0 | grep netmask | cut -b 9- | cut -d" " -f2
        echo "DockerIP : \c "
        ifconfig docker0 | grep netmask | cut -b 9- | cut -d" " -f2
        echo ""
        return
}
allip
```
-  __output :__
```

MyIp     : 721.0.1.5
vpnIP    : 10.10.10.11

```

