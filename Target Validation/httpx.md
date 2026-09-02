`httpx -l subdomains.txt` or `httpx -l subdomains.txt -tech-detect` - for web validation    

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ httpx -l subdomains.txt
[INF] Loading targets from subdomains.txt
[INF] Loaded 15 targets from subdomains.txt

[INF] Starting HTTP probe
[INF] [200] https://www.example.com [nginx]
[INF] [200] https://mail.example.com [nginx]
[INF] [200] https://blog.example.com [nginx]
[INF] [200] https://api.example.com [nginx]
[INF] [200] https://admin.example.com [nginx]
[INF] [200] https://dev.example.com [nginx]
[INF] [200] https://staging.example.com [nginx]
[INF] [200] https://test.example.com [nginx]
[INF] [200] https://support.example.com [nginx]
[INF] [200] https://webmail.example.com [nginx]
[INF] [404] https://ftp.example.com
[INF] [404] https://ns1.example.com
[INF] [404] https://ns2.example.com
[INF] [404] https://mx1.example.com
[INF] [404] https://mx2.example.com

[INF] HTTP probe completed in 12.3s
[INF] Found 10 live hosts
pentester@kali-linux:~$ httpx -l subdomains.txt -tech-detect
[INF] Loading targets from subdomains.txt
[INF] Loaded 15 targets from subdomains.txt
[INF] Technology detection enabled

[INF] Starting HTTP probe
[INF] [200] https://www.example.com [nginx,1.18.0] [Ubuntu]
[INF] [200] https://mail.example.com [nginx,1.18.0] [Ubuntu] [PHP,8.1]
[INF] [200] https://blog.example.com [nginx,1.18.0] [Ubuntu] [WordPress,6.2]
[INF] [200] https://api.example.com [nginx,1.18.0] [Ubuntu] [Node.js]
[INF] [200] https://admin.example.com [nginx,1.18.0] [Ubuntu] [Laravel,9.0]
[INF] [200] https://dev.example.com [nginx,1.18.0] [Ubuntu] [React]
[INF] [200] https://staging.example.com [nginx,1.18.0] [Ubuntu] [Django,4.1]
[INF] [200] https://test.example.com [nginx,1.18.0] [Ubuntu]
[INF] [200] https://support.example.com [nginx,1.18.0] [Ubuntu] [Zendesk]
[INF] [200] https://webmail.example.com [nginx,1.18.0] [Ubuntu] [Roundcube]

[INF] HTTP probe completed in 15.4s
[INF] Found 10 live hosts with technology detection
pentester@kali-linux:~$

```