`nc -v 192.168.56.201` - 22 (SSH banner)  
`telnet 192.168.56.206` - 5432 (PostgreSQL banner)  
`nc -w 3 192.168.56.202` - 21 (FTP banner)  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ nc -v 192.168.56.201 22
Connection to 192.168.56.201 port 22 [tcp/ssh] succeeded!
SSH-2.0-OpenSSH_7.9p1 Debian-10+deb10u2
Connection closed by foreign host.
pentester@kali-linux:~$ telnet 192.168.56.206 5432
Trying 192.168.56.206...
Connected to 192.168.56.206.
Escape character is '^]'.
PostgreSQL DB server ready
Connection closed by foreign host.
pentester@kali-linux:~$ nc -w 3 192.168.56.202 21
220 (vsftpd 2.3.4)
Connection closed by foreign host.
pentester@kali-linux:~$

```