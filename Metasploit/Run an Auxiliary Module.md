`msfconsole`    
`search auxiliary`  
`use auxiliary/scanner/portscan/tcp`  
`set RHOSTS 192.168.56.100-105`  
`run`

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ msfconsole
Metasploit Framework Console
       =[ metasploit v6.3.0-dev ]
msf6 >
msf6 > search auxiliary
Matching Modules:
  auxiliary/scanner/portscan/tcp
  auxiliary/scanner/ftp/ftp_version
  auxiliary/scanner/http/http_version
  auxiliary/scanner/ssh/ssh_version
  auxiliary/dos/tcp/synflood
msf6 > use auxiliary/scanner/portscan/tcp
Loaded module: auxiliary/scanner/portscan/tcp
msf6 > set RHOSTS
Usage: set <OPTION> <VALUE>
msf6 > set RHOSTS 192.168.56.100-105
Set RHOSTS => 192.168.56.100-105
msf6 > run
[*] 192.168.56.100:            - Scanned 1 of 1 hosts (100% complete)
[+] 192.168.56.101:            - 192.168.56.101:22 - TCP OPEN
[*] 192.168.56.101:            - Scanned 1 of 1 hosts (100% complete)
[+] 192.168.56.102:            - 192.168.56.102:21 - TCP OPEN
[*] 192.168.56.102:            - Scanned 1 of 1 hosts (100% complete)
[+] 192.168.56.103:            - 192.168.56.103:445 - TCP OPEN
[*] 192.168.56.103:            - Scanned 1 of 1 hosts (100% complete)
[*] 192.168.56.104:            - Scanned 1 of 1 hosts (100% complete)
[*] 192.168.56.105:            - Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed
msf6 >

```