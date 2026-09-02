`spiderfoot -s example.com` or `spiderfoot -M` to list modules  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ spiderfoot -s example.com
[*] SpiderFoot 4.0.0
[*] Starting scan for: example.com
[*] Using modules: sfp_whois, sfp_dnsresolve, sfp_dnsdb, sfp_subdomain_enum, sfp_ssl_certificate, sfp_web_framework, sfp_email_extractor

[+] sfp_whois: Found WHOIS data for example.com
[+] sfp_dnsresolve: Resolved 15 subdomains
[+] sfp_dnsdb: Found 8 additional subdomains from passive DNS
[+] sfp_subdomain_enum: Found 12 subdomains via enumeration
[+] sfp_ssl_certificate: Found SSL certificate data
[+] sfp_web_framework: Detected nginx web server
[+] sfp_email_extractor: Found 6 email addresses

[*] Scan completed in 45.2s
[*] Total results: 47
[*] Unique hosts: 23
[*] Email addresses: 6
[*] Subdomains: 35
pentester@kali-linux:~$ spiderfoot -M
Available SpiderFoot modules:

sfp_whois - WHOIS lookups
sfp_dnsresolve - DNS resolution
sfp_dnsdb - Passive DNS database
sfp_subdomain_enum - Subdomain enumeration
sfp_ssl_certificate - SSL certificate analysis
sfp_web_framework - Web framework detection
sfp_email_extractor - Email address extraction
sfp_social_media - Social media profile discovery
sfp_github - GitHub repository search
sfp_pastebin - Pastebin data search
sfp_breach_data - Data breach lookups
sfp_malware_check - Malware analysis
sfp_reputation - IP/domain reputation checks
sfp_geo_location - Geolocation data
sfp_cloud_storage - Cloud storage discovery

Total: 15 modules available
pentester@kali-linux:~$
```