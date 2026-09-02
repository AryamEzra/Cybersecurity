`naabu -host example.com` for a full scan, or `naabu -host example.com -p 80,443,22` for specific ports.  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ naabu -host example.com
[INF] Starting port scan for example.com
[INF] Found 5 open ports

93.184.216.34:80
93.184.216.34:443
93.184.216.34:25
93.184.216.34:993
93.184.216.34:995

[INF] Port scan completed in 8.2s
pentester@kali-linux:~$ naabu -host example.com -p 80,443,22
[INF] Starting port scan for example.com
[INF] Scanning ports: 80,443,22
[INF] Found 2 open ports

93.184.216.34:80
93.184.216.34:443

[INF] Port scan completed in 3.1s
pentester@kali-linux:~$

```