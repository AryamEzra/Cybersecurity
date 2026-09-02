`dig example.com NS`
`dig @ns1.example.com example.com AXFR`

```text

pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ dig example.com NS
; <<>> DiG 9.18.1-1ubuntu1.3-Ubuntu <<>> example.com NS
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12352
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;example.com.		IN	NS

;; ANSWER SECTION:
example.com.	3600	IN	NS	ns1.example.com.
example.com.	3600	IN	NS	ns2.example.com.

;; Query time: 18 msec
;; SERVER: 127.0.0.53#53(127.0.0.53)
;; WHEN: Mon Jun 24 12:00:00 UTC 2024
;; MSG SIZE  rcvd: 89
pentester@kali-linux:~$ dig @ns1.example.com example.com AXFR
; <<>> DiG 9.18.1-1ubuntu1.3-Ubuntu <<>> @ns1.example.com example.com AXFR
; (1 server found)
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12350
;; flags: qr aa; QUERY: 1, ANSWER: 5, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;example.com.		IN	AXFR

;; ANSWER SECTION:
example.com.	3600	IN	A	93.184.216.34
example.com.	3600	IN	MX	10 mail.example.com.
example.com.	3600	IN	TXT	"v=spf1 include:_spf.example.com ~all"
example.com.	3600	IN	NS	ns1.example.com.
example.com.	3600	IN	NS	ns2.example.com.

;; Query time: 25 msec
;; SERVER: ns1.example.com#53(ns1.example.com)
;; WHEN: Mon Jun 24 12:00:00 UTC 2024
;; MSG SIZE  rcvd: 234

; Transfer completed.
pentester@kali-linux:~$ nslookup -type=AXFR example.com ns1.example.com
Server:  ns1.example.com
Address: 192.168.56.10#53

example.com	zone = 5 records
example.com.	3600	IN	A	93.184.216.34
example.com.	3600	IN	MX	10 mail.example.com.
example.com.	3600	IN	TXT	"v=spf1 include:_spf.example.com ~all"
example.com.	3600	IN	NS	ns1.example.com.
example.com.	3600	IN	NS	ns2.example.com.

;; Received 5 records.
pentester@kali-linux:~$

```