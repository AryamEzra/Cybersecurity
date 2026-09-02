1. Victim Start SSH server: `systemctl start ssh`  
2. Attacker Create SOCKS proxy: `ssh -D 1080 admin@192.168.1.100` - SOCKS proxy established via SSH dynamic port forwarding    
3. Attacker Test proxy with curl: `curl --socks5 localhost:1080 http://internal-web.local` - nternal service accessed through SOCKS proxy   
4. Attacker Compare IP addresses: `curl https://ifconfig.me` vs `curl --socks5 localhost:1080 https://ifconfig.me`  

```text
Victim Machine (192.168.1.100)
Welcome to Ubuntu 20.04.3 LTS
victim@target:~$ 
victim@target:~$ systemctl start ssh
● ssh.service - OpenBSD Secure Shell server
   Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vendor preset: enabled)
   Active: active (running) since Mon 2021-12-13 10:30:15 UTC; 2s ago
     Docs: man:sshd(8)
           man:sshd_config(5)
 Main PID: 1234 (sshd)
    Tasks: 1 (limit: 4915)
   CGroup: /system.slice/ssh.service
           └─1234 /usr/sbin/sshd -D
victim@target:~$ 
victim@target:~$
```

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ ssh -D 1080 admin@192.168.1.100
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-74-generic x86_64)

* Documentation:  https://help.ubuntu.com/
* Management:     https://landscape.canonical.com/
* Support:        https://ubuntu.com/advantage

Last login: Mon Dec 13 10:30:15 2021 from 192.168.1.50
Dynamic forwarding established on localhost:1080
admin@192.168.1.100:~$ 
admin@192.168.1.100:~$ curl --socks5 localhost:1080 http://internal-web.local
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1024

<!DOCTYPE html>
<html>
<head><title>Internal Service</title></head>
<body>
<h1>Welcome to internal-web.local</h1>
<p>This service is accessible through the SOCKS proxy.</p>
</body>
</html>
admin@192.168.1.100:~$ curl https://ifconfig.me
203.0.113.45
admin@192.168.1.100:~$ curl --socks5 localhost:1080 https://ifconfig.me
192.168.1.100
admin@192.168.1.100:~$

```