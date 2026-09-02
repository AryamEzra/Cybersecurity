`nc -v 192.168.56.101 21`  
`telnet 192.168.56.103 23`  

``` text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ nc -v 192.168.56.101 21
Connection to 192.168.56.101 port 21 [tcp/ftp] succeeded!
220 (vsftpd 2.3.4)
Connection closed by foreign host.
pentester@kali-linux:~$ telnet 192.168.56.103 23
Trying 192.168.56.103...
Connected to 192.168.56.103.
Escape character is '^]'.
Welcome to Telnet Server
Connection closed by foreign host.
pentester@kali-linux:~$


```