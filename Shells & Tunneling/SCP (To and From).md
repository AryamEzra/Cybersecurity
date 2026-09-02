1. On the victim terminal, start the SSH server: `systemctl start ssh`  
2. On the attacker terminal, upload a file: `scp local_file.txt admin@192.168.1.100:/tmp/`  
2. On the attacker terminal, download a file: `scp admin@192.168.1.100:/home/admin/secret.txt .`  

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
pentester@kali-linux:~$ scp local_file.txt admin@192.168.1.100:/tmp/
local_file.txt 100% 1024 1.0MB/s 00:00
pentester@kali-linux:~$ scp admin@192.168.1.100:/home/admin/secret.txt .
/home/admin/secret.txt                                    100%   44     1.0KB/s   00:00
pentester@kali-linux:~$
```