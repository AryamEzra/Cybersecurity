1. `recon-ng` - Start the framework  
2. `workspaces add example_target` - Create workspace  
3. `use recon/profiles-profiles/name_to_domain` - Load module  
4. `set SOURCE example.com` - Set the target  
5. `run` - Execute the module  
6. `show hosts` - View results  

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ recon-ng
[*] Recon-ng v5.2.0
[*] No workspace selected.
[*] No modules loaded.

[recon-ng][default] > 
pentester@kali-linux:~$ workspaces add example_target
[+] Workspace 'example_target' added.
[+] Workspace 'example_target' selected.
[recon-ng][example_target] > 
pentester@kali-linux:~$ use recon/profiles-profiles/name_to_domain
[recon-ng][example_target][name_to_domain] > 
pentester@kali-linux:~$ set SOURCE example.com
SOURCE => example.com
[recon-ng][example_target][name_to_domain] > 
pentester@kali-linux:~$ run
[*] Running module 'name_to_domain'...
[*] Searching for domain information...
[+] www.example.com - Found subdomain
[+] mail.example.com - Found subdomain
[+] api.example.com - Found subdomain
[+] admin.example.com - Found subdomain
[+] ftp.example.com - Found subdomain
[*] Module execution completed.
[recon-ng][example_target][name_to_domain] > 
pentester@kali-linux:~$ show hosts

  +-------------------------------------------------------------------+
  | rowid | host           | ip_address | region | country | latitude | longitude |
  +-------------------------------------------------------------------+
  | 1     | www.example.com | 93.184.216.34 | US     | US      | 37.4056  | -122.0775 |
  | 2     | mail.example.com | 93.184.216.34 | US     | US      | 37.4056  | -122.0775 |
  | 3     | api.example.com | 93.184.216.34 | US     | US      | 37.4056  | -122.0775 |
  | 4     | admin.example.com | 93.184.216.34 | US     | US      | 37.4056  | -122.0775 |
  | 5     | ftp.example.com | 93.184.216.34 | US     | US      | 37.4056  | -122.0775 |
  +-------------------------------------------------------------------+

[recon-ng][example_target][name_to_domain] > 
pentester@kali-linux:~$
```