1. Victim Start SSH server: `systemctl start ssh`  
2. Attacker Create SOCKS proxy: `ssh -D 1080 admin@192.168.1.100` - SOCKS proxy established  
3. Attacker Check proxychains config: `cat /etc/proxychains.conf` -  Proxychains used successfully  
4. Attacker Use proxychains: `proxychains nmap -sT -p 80 internal-web.local`- Internal service accessed through proxychains  
5. Attacker Test IP difference: `proxychains curl https://ifconfig.me`  

```text
Victim Machine (192.168.1.100)
Welcome to Ubuntu 20.04.3 LTS
victim@target:~$ 
victim@target:~$ systemctl start ssh
● ssh.service - OpenBSD Secure Shell server
   Active: active (running) since Mon 2021-12-13 10:30:15 UTC; 2s ago
victim@target:~$ 
```


```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ ssh -D 1080 admin@192.168.1.100
Welcome to Ubuntu 20.04.3 LTS
Dynamic forwarding established on localhost:1080
admin@192.168.1.100:~$ 
admin@192.168.1.100:~$ cat /etc/proxychains.conf
# proxychains.conf  VER 4.x
#
#        HTTP, SOCKS4, SOCKS5 tunneling proxifier with DNS.
#

# The option below identifies how the ProxyList is treated.
# only one option should be uncommented at time,
# otherwise the last appearing option will be accepted
#
#dynamic_chain
#
# Dynamic - Each connection will be done via chained proxies
# all proxies chained in the order as they appear in the list
# at least one proxy must be online to play in chain
# (dead proxies are skipped)
# otherwise EINTR is returned to the app
#
strict_chain
#
# Strict - Each connection will be done via chained proxies
# all proxies chained in the order as they appear in the list
# all proxies must be online to play in chain
# otherwise EINTR is returned to the app
#
#random_chain
#
# Random - Each connection will be done via random proxy
# (or proxy chain, see  chain_len) from the list.
# this option is good to test your IDS :)

# Make sense only if random_chain
#chain_len = 2

# Quiet mode (no output from library)
#quiet_mode

# Proxy DNS requests - no leak for DNS data
proxy_dns

# Some timeouts in milliseconds
tcp_connect_time_out 8000
tcp_read_time_out 8000

# ProxyList format
#       type  host  port [user pass]
#       (values separated by 'tab' or 'blank')
#
#
#        Examples:
#
#            	socks5	192.168.67.78	1080	lamer	secret
#		http	192.168.89.3	8080	justu	hidden
#	 	socks4	192.168.1.49	1080
#	        http	192.168.39.93	8080
#
#
#       proxy types: http, socks4, socks5
#        ( auth types: user/pass )
#
[ProxyList]
# add proxy here ...
# meanwile
# defaults set to "tor"
socks5 127.0.0.1 1080
admin@192.168.1.100:~$ proxychains nmap -sT -p 80 internal-web.local
[proxychains] config file found: /etc/proxychains.conf
[proxychains] preloading /usr/lib/x86_64-linux-gnu/libproxychains.so.4
[proxychains] DLL init: proxychains-ng 4.14
[proxychains] Dynamic chain  ...  127.0.0.1:1080  ...  OK
Starting Nmap 7.80 ( https://nmap.org ) at 2021-12-13 10:30 UTC
Nmap scan report for internal-web.local (192.168.1.200)
Host is up (0.001s latency).

PORT   STATE SERVICE
80/tcp open  http

Nmap done: 1 IP address (1 host up) scanned in 1.23 seconds
admin@192.168.1.100:~$ proxychains curl https://ifconfig.me
[proxychains] config file found: /etc/proxychains.conf
[proxychains] preloading /usr/lib/x86_64-linux-gnu/libproxychains.so.4
[proxychains] DLL init: proxychains-ng 4.14
[proxychains] Dynamic chain  ...  127.0.0.1:1080  ...  OK
192.168.1.100
admin@192.168.1.100:~$
```