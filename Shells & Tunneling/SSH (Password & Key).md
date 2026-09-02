1. On the victim terminal, start the SSH server: `systemctl start ssh`  
2. On the attacker terminal, connect with password: `ssh admin@192.168.1.100`  
3. On the attacker terminal, connect with key: `ssh -i user_key.pem user@192.168.1.100`  

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
pentester@kali-linux:~$ ssh admin@192.168.1.100
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-74-generic x86_64)

* Documentation:  https://help.ubuntu.com/
* Management:     https://landscape.canonical.com/
* Support:        https://ubuntu.com/advantage

Last login: Mon Dec 13 10:30:15 2021 from 192.168.1.50
admin@192.168.1.100:~$ 
admin@192.168.1.100:~$ ssh -i user_key.pem user@192.168.1.100
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-74-generic x86_64)

* Documentation:  https://help.ubuntu.com/
* Management:     https://landscape.canonical.com/
* Support:        https://ubuntu.com/advantage

Last login: Mon Dec 13 10:30:15 2021 from 192.168.1.50
user@192.168.1.100:~$ 
user@192.168.1.100:~$
```