Ans: Using dig to query DNS records  
`dig example.com` - this is the deafault A  
`dig example.com MX` or  
`dig example.com TXT` or  
`dig example.com NS`  

```text

pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ dig example.com
; <<>> DiG 9.16.1-Ubuntu <<>> example.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12345
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;example.com.			IN	A

;; ANSWER SECTION:
example.com.		86400	IN	A	93.184.216.34

;; Query time: 15 msec
;; SERVER: 127.0.0.53#53(127.0.0.53)
;; WHEN: Mon Jan 01 12:00:00 UTC 2024
;; MSG SIZE  rcvd: 56
pentester@kali-linux:~$

```