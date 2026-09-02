`nuclei -l live_hosts.txt` or `nuclei -l live_hosts.txt -t exposures/`  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ nuclei -l live_hosts.txt
[INF] Loading templates from /root/nuclei-templates
[INF] Loaded 1000+ templates
[INF] Starting scan with 10 hosts

[LOW] [http] https://www.example.com/ [nginx-version]
[LOW] [http] https://mail.example.com/ [nginx-version]
[LOW] [http] https://blog.example.com/ [nginx-version]
[LOW] [http] https://api.example.com/ [nginx-version]
[LOW] [http] https://admin.example.com/ [nginx-version]
[MEDIUM] [http] https://dev.example.com/ [exposed-panel]
[MEDIUM] [http] https://staging.example.com/ [exposed-panel]
[INFO] [http] https://test.example.com/ [tech-detect:nginx]
[INFO] [http] https://support.example.com/ [tech-detect:nginx]
[INFO] [http] https://webmail.example.com/ [tech-detect:nginx]

[INF] Scan completed in 45.2s
[INF] Found 9 vulnerabilities
pentester@kali-linux:~$ nuclei -l live_hosts.txt -t exposures/
[INF] Loading templates from exposures/
[INF] Loaded 150+ exposure templates
[INF] Starting scan with 10 hosts

[MEDIUM] [http] https://dev.example.com/ [exposed-panel]
[MEDIUM] [http] https://staging.example.com/ [exposed-panel]
[HIGH] [http] https://admin.example.com/ [admin-panel-exposure]
[LOW] [http] https://test.example.com/ [debug-exposure]

[INF] Scan completed in 18.7s
[INF] Found 4 exposure vulnerabilities
pentester@kali-linux:~$

```