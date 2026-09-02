`curl https://example.com` or `wget https://example.com`  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ curl https://example.com
<!DOCTYPE html>
<html>
<head><title>Example Domain</title></head>
<body>
<h1>Example Domain</h1>
<p>This domain is for use in illustrative examples in documents.</p>
</body>
</html>
pentester@kali-linux:~$ wget https://example.com
--2024-06-01 10:30:15--  https://example.com/
Resolving example.com (example.com)... 93.184.216.34
Connecting to example.com (example.com)|93.184.216.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1256 (1.2K) [text/html]
Saving to: 'index.html'

100%[======================================>] 1,256       --.-K/s   in 0s      

2024-06-01 10:30:15 (1.2 MB/s) - 'index.html' saved [1256/1256]
pentester@kali-linux:~$
```