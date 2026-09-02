Start msfconsole - `msfconsole`  
Run help - `help`  
Run search - `search windows`, `search smb`  
Run use with a valid module - `use exploit/windows/smb/ms17_010_eternalblue`, `use exploit/windows/smb/ms17_010_eternalblue`    

```text
pentester@kali-linux:~$ Welcome to the Kali Terminal Simulation!
Type help to see available commands.
pentester@kali-linux:~$ msfconsole
Metasploit Framework Console
       =[ metasploit v6.3.0-dev ]
msf6 >
msf6 > help
Core Commands:
  help        Display this help menu
  search      Search module names/descriptions
  use         Select a module by name
  set         Set a context-specific variable
  show options  Show available options for the current module
  run/exploit Run the current module
  exit        Exit the console
msf6 > search
Usage: search <term>
msf6 > use
Usage: use <module>
msf6 > show options
No module selected. Use the use command first.
msf6 > search windows
Matching Modules:
  exploit/windows/smb/ms17_010_eternalblue
msf6 > use exploit/windows/smb/ms17_010_eternalblue
Loaded module: exploit/windows/smb/ms17_010_eternalblue
msf6 > search smb
Matching Modules:
  exploit/windows/smb/ms17_010_eternalblue
msf6 > use exploit/windows/smb/ms17_010_eternalblue
Loaded module: exploit/windows/smb/ms17_010_eternalblue
msf6 >
```