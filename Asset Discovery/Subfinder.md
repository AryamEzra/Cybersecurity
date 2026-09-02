`subfinder -d example.com` or 
`subfinder -d example.com -all`

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ subfinder -d example.com
[INF] Loading provider config from /root/.config/subfinder/provider-config.yaml
[INF] Enumerating subdomains for example.com

[INF] Found 15 subdomains for example.com

www.example.com
mail.example.com
ftp.example.com
blog.example.com
api.example.com
admin.example.com
dev.example.com
staging.example.com
test.example.com
support.example.com
ns1.example.com
ns2.example.com
mx1.example.com
mx2.example.com
webmail.example.com

[INF] Enumeration completed in 2.3s
pentester@kali-linux:~$ subfinder -d example.com -all
[INF] Loading provider config from /root/.config/subfinder/provider-config.yaml
[INF] Enumerating subdomains for example.com
[INF] Using all available sources

[INF] Found 23 subdomains for example.com

www.example.com
mail.example.com
ftp.example.com
blog.example.com
api.example.com
admin.example.com
dev.example.com
staging.example.com
test.example.com
support.example.com
ns1.example.com
ns2.example.com
mx1.example.com
mx2.example.com
webmail.example.com
app.example.com
cdn.example.com
images.example.com
static.example.com
www2.example.com
old.example.com
archive.example.com
backup.example.com

[INF] Enumeration completed in 4.8s
pentester@kali-linux:~$
```