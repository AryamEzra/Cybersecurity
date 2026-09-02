`curl -L http://httpbin.org/redirect/1`  
`curl -i -L http://httpbin.org/redirect/1`  
`curl -d 'name=test' -X POST https://httpbin.org/post`  
`curl -A \"MyAgent\" https://example.com`  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ curl -L http://httpbin.org/redirect/1
{
  "args": {},
  "headers": {
    "Accept": "*/*",
    "Host": "httpbin.org",
    "User-Agent": "curl/7.68.0"
  },
  "origin": "203.0.113.1",
  "url": "http://httpbin.org/get"
}
pentester@kali-linux:~$ curl -i -L http://httpbin.org/redirect/1
HTTP/1.1 302 FOUND
Location: /get
Content-Type: text/html; charset=utf-8
Content-Length: 0
Server: gunicorn/19.9.0
Date: Sat, 01 Jun 2024 10:30:15 GMT

HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 234
Server: gunicorn/19.9.0
Date: Sat, 01 Jun 2024 10:30:15 GMT

{
  "args": {},
  "headers": {
    "Accept": "*/*",
    "Host": "httpbin.org",
    "User-Agent": "curl/7.68.0"
  },
  "origin": "203.0.113.1",
  "url": "http://httpbin.org/get"
}
pentester@kali-linux:~$ curl -d 'name=test' -X POST https://httpbin.org/post
{
  "args": {},
  "data": "",
  "files": {},
  "form": {
    "name": "test"
  },
  "headers": {
    "Accept": "*/*",
    "Content-Length": "9",
    "Content-Type": "application/x-www-form-urlencoded",
    "Host": "httpbin.org",
    "User-Agent": "curl/7.68.0"
  },
  "json": null,
  "origin": "203.0.113.1",
  "url": "https://httpbin.org/post"
}
pentester@kali-linux:~$ curl -A \"MyAgent\" https://example.com
Command not found: curl -A \"MyAgent\" https://example.com
pentester@kali-linux:~$
```