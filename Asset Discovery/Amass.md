Amass - Advanced Subdomain Enumeration  
`amass enum -d example.com` - for basic enumeration  
`amass intel -d example.com` - for intelligence gathering  
`amass enum -h` - to see all available options  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ amass enum -d example.com
[INFO] Configuration loaded from: /root/.config/amass/config.ini
[INFO] Starting enumeration of example.com
[INFO] Found: www.example.com
[INFO] Found: mail.example.com
[INFO] Found: ftp.example.com
[INFO] Found: blog.example.com
[INFO] Found: api.example.com
[INFO] Found: admin.example.com
[INFO] Found: dev.example.com
[INFO] Found: staging.example.com
[INFO] Found: test.example.com
[INFO] Found: support.example.com
[INFO] Found: ns1.example.com
[INFO] Found: ns2.example.com
[INFO] Found: mx1.example.com
[INFO] Found: mx2.example.com
[INFO] Found: webmail.example.com
[INFO] Found: cdn.example.com
[INFO] Found: assets.example.com
[INFO] Found: images.example.com
[INFO] The enumeration has finished
pentester@kali-linux:~$ amass intel -d example.com
[INFO] Configuration loaded from: /root/.config/amass/config.ini
[INFO] Starting intelligence gathering for example.com
[INFO] ASN: 12345 - Example Corp
[INFO] CIDR: 192.168.1.0/24
[INFO] Found related domain: example.org
[INFO] Found related domain: example.net
[INFO] Found related domain: examplecorp.com
[INFO] Intelligence gathering finished
pentester@kali-linux:~$ amass enum -h
Usage: amass enum [flags]

Flags:
  -active                 Enable active recon methods
  -brute                  Enable brute force subdomain enumeration
  -d, --domain strings    Domain names separated by commas (can be used multiple times)
  -exclude-sources string Sources to exclude from enumeration
  -include-sources string Sources to include in enumeration
  -ip                     Show the IP addresses for discovered names
  -o, --output string     Path to the output file
  -passive                Only passive recon methods
  -silent                 Disable all output except the results
  -src                    Print data sources for the discovered names
  -timeout int            Number of minutes to execute the enumeration
  -v                      Output status / debug / troubleshooting info

Examples:
  amass enum -d example.com
  amass enum -d example.com -o results.txt
  amass enum -d example.com -passive
  amass enum -d example.com -active -brute
pentester@kali-linux:~$

```