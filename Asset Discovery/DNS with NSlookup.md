A - `nslookup example.com`  
MX - `nslookup -type=MX example.com`  
TXT - `nslookup -type=TXT example.com`  
NS - `nslookup -type=NS example.com`  
PTR - `nslookup 93.184.216.34` - had to use the address below the name from the `nslookup.example`  


```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ nslookup example.com
Server:  192.168.56.1
Address: 192.168.56.1#53

Name:    example.com
Address: 93.184.216.34
pentester@kali-linux:~$ nslookup -type=MX example.com
Server:  192.168.56.1
Address: 192.168.56.1#53

example.com	mail exchanger = mail.example.com
pentester@kali-linux:~$ nslookup -type=TXT example.com
Server:  192.168.56.1
Address: 192.168.56.1#53

example.com	text = "v=spf1 include:_spf.example.com ~all"
pentester@kali-linux:~$ nslookup -type=PTR 1.56.168.192.in-addr.arpa
Command not found: nslookup -type=PTR 1.56.168.192.in-addr.arpa
pentester@kali-linux:~$ nslookup example.com 192.168.56.1
Command not found: nslookup example.com 192.168.56.1
pentester@kali-linux:~$ nslookup 192.168.56.1
Command not found: nslookup 192.168.56.1
pentester@kali-linux:~$ nslookup 1.56.168.192
Command not found: nslookup 1.56.168.192
pentester@kali-linux:~$ nslookup -type=PTR 34.216.184.93.in-addr.arpa
Command not found: nslookup -type=PTR 34.216.184.93.in-addr.arpa
pentester@kali-linux:~$ nslookup -type=PTR example.com
Command not found: nslookup -type=PTR example.com
pentester@kali-linux:~$ nslookup example.com
Server:  192.168.56.1
Address: 192.168.56.1#53

Name:    example.com
Address: 93.184.216.34
pentester@kali-linux:~$ nslookup 192.168.56.1
Command not found: nslookup 192.168.56.1
pentester@kali-linux:~$ nslookup 93.184.216.34
Server:  192.168.56.1
Address: 192.168.56.1#53

93.184.216.34.in-addr.arpa	name = example.com
pentester@kali-linux:~$


```