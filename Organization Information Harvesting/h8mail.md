`h8mail -t example.com` or   
`h8mail -t admin@example.com`  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ h8mail -t example.com
[+] h8mail v2.5.6 - Email OSINT & Password breach hunting
[+] Target: example.com
[+] Starting email enumeration...

[+] Found emails:
admin@example.com
contact@example.com
info@example.com
support@example.com
webmaster@example.com
john.doe@example.com
jane.smith@example.com
marketing@example.com
sales@example.com

[+] Checking for password breaches...
[+] admin@example.com: Found in 2 breaches
[+] contact@example.com: Found in 1 breach
[+] info@example.com: Found in 3 breaches
[+] support@example.com: Clean
[+] webmaster@example.com: Found in 1 breach
[+] john.doe@example.com: Found in 4 breaches
[+] jane.smith@example.com: Found in 2 breaches
[+] marketing@example.com: Clean
[+] sales@example.com: Found in 1 breach

[+] Email enumeration completed
[+] Total emails found: 9
[+] Breached emails: 7
pentester@kali-linux:~$ h8mail -t admin@example.com
[+] h8mail v2.5.6 - Email OSINT & Password breach hunting
[+] Target: admin@example.com
[+] Starting breach analysis...

[+] Email: admin@example.com
[+] Checking password breaches...
[+] Found in 3 data breaches:
  - LinkedIn (2012)
  - Adobe (2013)
  - Collection #1 (2019)

[+] Associated passwords:
  - password123
  - admin2021
  - welcome123

[+] Analysis completed
[+] Total breaches: 3
[+] Passwords found: 3
pentester@kali-linux:~$

```