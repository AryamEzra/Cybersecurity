`theHarvester -d example.com -b all` or   
`theHarvester -d example.com -b google`

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ theHarvester -d example.com -b all
[*] Target: example.com
[*] Searching Bing.
[*] Searching BingAPI.
[*] Searching Bufferoverun.
[*] Searching Censys.
[*] Searching Certspotter.
[*] Searching Crtsh.
[*] Searching Dnsdumpster.
[*] Searching Duckduckgo.
[*] Searching Fullhunt.
[*] Searching Github.
[*] Searching Google.
[*] Searching Hackertarget.
[*] Searching Hunter.
[*] Searching Intelx.
[*] Searching Linkedin.
[*] Searching Linkedin2.
[*] Searching Netcraft.
[*] Searching Otx.
[*] Searching PTRarchive.
[*] Searching Securitytrails.
[*] Searching Shodan.
[*] Searching Threatcrowd.
[*] Searching Threatminer.
[*] Searching Trello.
[*] Searching Twitter.
[*] Searching Urlscan.
[*] Searching Virustotal.
[*] Searching Yahoo.

[*] No IPs found.

[*] Emails found: 5
admin@example.com
contact@example.com
info@example.com
support@example.com
webmaster@example.com

[*] Hosts found: 8
www.example.com
mail.example.com
ftp.example.com
blog.example.com
api.example.com
admin.example.com
dev.example.com
staging.example.com
pentester@kali-linux:~$ theHarvester -d example.com -b google
[*] Target: example.com
[*] Searching Google.

[*] No IPs found.

[*] Emails found: 3
admin@example.com
contact@example.com
info@example.com

[*] Hosts found: 5
www.example.com
mail.example.com
blog.example.com
api.example.com
admin.example.com
pentester@kali-linux:~$

```