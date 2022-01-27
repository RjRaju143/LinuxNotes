
> # _RjRaju_

# Open-SSH

## install openssh-client
```bash
sudo apt-get install openssh-client
```

## install openssh-server
```bash
sudo apt-get install openssh-server
```

# SSH-Config File
## client config
```bash
cat /etc/ssh/ssh_config
ssh user@$IP
sudo nano /etc/ssh/sshd_config

# PermitRootLogin no 
# MaxAutthentication 3
# MaxSessions 3
```
# restart sshd
```bash
sudo systemctl restart sshd.server
```
# Lock the Root Passwd & Disable passwd login
```
sudo passwd -l root
sudo passwd -S root # check the status
```
## SSH-key

```bash
ssh-keygen -t rsa
ssh-copy-id admin@$IP
```
<!-- store your public key in the server & private key in client -->

# SCP -Secured-COPT

```bash
scp filename.txt user@$IP:/server/location
scp test.txt onmyway@192.168.55.1:/home/admin/
```
---
# SSH-PORT FORWARDING

```bash
ssh-keygen
ssh -R 80:localhost:8000 localhost.run
```
```
ssh -R 80:localhost:[PortToForward] localhost.run
```
```
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/user/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/user/.ssh/id_rsa
Your public key has been saved in /home/user/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:SqRt0EXQwMrfaGccHfGaTf383WQst8lVUyfEtaCV6VI user@linux
The key's randomart image is:
+---[RSA 3072]----+
|     .o=o .. ==.+|
|     .... ..oEo.+|
|   ...o  . o= .o.|
|    o=  . .* . +o|
|    ..++S.o o . O|
|     o+.=     .=B|
|     ..o       ++|
|                 |
|                 |
+----[SHA256]-----+
```
```
$ ssh -R 80:localhost:8000 localhost.run
The authenticity of host 'localhost.run (35.171.254.69)' can't be established.
RSA key fingerprint is SHA256:FV8IMJ4IYjYUTnd6on7PqbRjaZf4c1EhhEBgeUdE94I.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'localhost.run' (RSA) to the list of known hosts.

===============================================================================
Welcome to localhost.run!

Follow your favourite reverse tunnel at [https://twitter.com/localhost_run].

**You need a SSH key to access this service.**
If you get a permission denied follow Gitlab's most excellent howto:
https://docs.gitlab.com/ee/ssh/
*Only rsa and ed25519 keys are supported*

To set up and manage custom domains go to https://admin.localhost.run/

More details on custom domains (and how to enable subdomains of your custom
domain) at https://localhost.run/docs/custom-domains

To explore using localhost.run visit the documentation site:
https://localhost.run/docs/

===============================================================================


** your connection id is 0cd98ba8-0c86-43e4-9aa2-3ad146b46c72, please mention it if you send me a message about an issue. **

007caefb4910be.lhr.life tunneled with tls termination, https://007caefb4910be.lhr.life
```
---
## **SSH**
----------
-   print actives network connections: `netstat -tulpn`, for pid informations, use `sudo netstat -tulpn`
-   print where the ssh program is lcoated: `which sshd`
-   check if ssh is running: `systemctl status ssh`
-   to connect to a remote machine via ssh: `ssh username@1.2.3.4` where `1.2.3.4` is the ip adress of the remote machine, the user will be asked to enter the password of the guven user. it is recommended to disallow password authentication and root access to the machine, a better way is to use public/private key authentication.
-   `ssh -i publickey.pem username@1.2.3.4` to log in using ssh with the given public key.
-   `ssh -v -i publickey.pem username@1.2.3.4` to log in using ssh with the given public key in debug mode, we get more details on the terminal, with that debug mode, if there is some issue to connect via ssh, the output can be helpful.
-   `ssh -p 33 username@1.2.3.4`: to connect via ssh on a customized port, normally the default port is `22`.
-   default configuration of ssh in the server: `/etc/ssh/sshd_config`.
-   to check the logs of authentication to the server: `/var/log/auth.log`.
-   on the client side, when connecting via `ssh` to a remote server, a folder named `.ssh` will be created and will contains the following files:
    -   `known_hosts`: hosts that the client already connected to via `ssh`.
    -   `id_rsa`: private key.
    -   `id_rsa.pub`: public key.
-   ssh server configuration:
    -   the config file to edit is `/etc/sshd_config`.
    -   we can edit some configurations like port number, prohibit root login, no user/password authentication….
    -   We can allow only some users or groups to connect via ssh with `AllowsUsers groupname user1 user2`
-   keys generation:
    -   ssh-key-gen: to generate new keys, by default they will be placed inside `.ssh` folder, `id_rsa` as default name of the private key, `id_rsa.pub` as default public key name, the private key should be kept private.
-   `ssh-copy-id -i /.ssh/id_rsa.pub username@1.2.3.4`: to copy the public to the remote ssh server, with that further logging will succeed without passing password or publickey.
-   `ssh-copy-id` will copy our public key to the remote `/.ssh/authorized_keys` file in the ssh server. In the authorized_keys file, every line represent a client ssh public key.
---
