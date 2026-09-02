`curl -k https://self-signed.badssl.com/` or `wget --no-check-certificate https://self-signed.badssl.com/`

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ curl -k https://self-signed.badssl.com/
<!DOCTYPE html>
<html>
<head><title>self-signed.badssl.com</title></head>
<body>
<h1>self-signed.badssl.com</h1>
<p>This page uses a self-signed certificate.</p>
</body>
</html>
pentester@kali-linux:~$ wget --no-check-certificate https://self-signed.badssl.com/
--2024-06-01 10:30:15--  https://self-signed.badssl.com/
Resolving self-signed.badssl.com (self-signed.badssl.com)... 104.154.89.105
Connecting to self-signed.badssl.com (104.154.89.105)|104.154.89.105|:443... connected.
WARNING: cannot verify self-signed.badssl.com's certificate, issued by 'CN=badssl.com':
  Self-signed certificate encountered.
HTTP request sent, awaiting response... 200 OK
Length: 1234 (1.2K) [text/html]
Saving to: 'index.html'

100%[======================================>] 1,234       --.-K/s   in 0s      

2024-06-01 10:30:15 (1.2 MB/s) - 'index.html' saved [1234/1234]
pentester@kali-linux:~$

```