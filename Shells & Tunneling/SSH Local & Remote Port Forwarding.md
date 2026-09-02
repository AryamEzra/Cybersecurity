1. Victim Start SSH server: `systemctl start ssh`  
2. Victim Start internal service: `nc -l -p 80`   
3. Attacker Create local port forward: `ssh -L 8080:internal-web.local:80 admin@192.168.1.100` - Local port forwarding established  
4. Attacker Create remote port forward: `ssh -R 2222:localhost:22 admin@192.168.1.100` - Remote port forwarding established  
5. Test service: `curl http://localhost:8080` - Internal service accessed

```text
ictim Machine (192.168.1.100)
Welcome to Ubuntu 20.04.3 LTS
victim@target:~$ 
victim@target:~$ systemctl start ssh
● ssh.service - OpenBSD Secure Shell server
   Active: active (running) since Mon 2021-12-13 10:30:15 UTC; 2s ago
victim@target:~$ 
victim@target:~$ nc -l -p 80
Listening on [0.0.0.0] (family 0, port 80)
Internal service listener started on port 80
victim@target:~$ 
victim@target:~$

```


```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ ssh -L 8080:internal-web.local:80 admin@192.168.1.100
Welcome to Ubuntu 20.04.3 LTS
Local port forwarding established: localhost:8080 -> internal-web.local:80
admin@192.168.1.100:~$ 
admin@192.168.1.100:~$ ssh -R 2222:localhost:22 admin@192.168.1.100
Welcome to Ubuntu 20.04.3 LTS
Remote port forwarding established: 192.168.1.100:2222 -> localhost:22
admin@192.168.1.100:~$ 
admin@192.168.1.100:~$ curl http://localhost:8080
HTTP/1.1 200 OK
Content-Type: text/html

<!DOCTYPE html>
<html>
<head><title>Internal Service</title></head>
<body>
<h1>Welcome to Internal Service</h1>
<p>Successfully accessed through SSH local port forwarding!</p>
</body>
</html>
admin@192.168.1.100:~$

```