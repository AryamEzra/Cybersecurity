`curl -I https://example.com` or `wget --server-response https://example.com`  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ curl -I https://example.com
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Content-Length: 1256
Server: ECS (nyb/1D2B)
Date: Sat, 01 Jun 2024 10:30:15 GMT
Connection: keep-alive
pentester@kali-linux:~$ wget --server-response https://example.com
--2024-06-01 10:30:15--  https://example.com/
Resolving example.com (example.com)... 93.184.216.34
Connecting to example.com (example.com)|93.184.216.34|:443... connected.
HTTP request sent, awaiting response... 
  HTTP/1.1 200 OK
  Content-Type: text/html; charset=UTF-8
  Content-Length: 1256
  Server: ECS (nyb/1D2B)
  Date: Sat, 01 Jun 2024 10:30:15 GMT
  Connection: keep-alive
Length: 1256 (1.2K) [text/html]
Saving to: 'index.html'

100%[======================================>] 1,256       --.-K/s   in 0s      

2024-06-01 10:30:15 (1.2 MB/s) - 'index.html' saved [1256/1256]
pentester@kali-linux:~$

```