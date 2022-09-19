Ignite - TryHackMe

Tags: `ctf`,`boot2root`, `privesc`, `exploit`

Target IP: 10.10.250.119

Goals:
- `user.txt`
- `root.txt`

## nmap

`nmap -sV -sC 10.10.250.119`

- p80 (http)(fuel CMS 1.4)
- robots.txt disallowed
- - /fuel/
-

	
## gobuster

- /@
- /0
- /assets
- /home
- /index
- /index.php
- /lost+found
- /offline
- /robots.txt
- /server-status
- /


`gobuster dir -u http://10.10.250.119 -w /usr/share/wordlists/dirb/common.txt`

`gobuster dir -u http://10.10.250.119/fuel -w /usr/share/wordlists/dirb/common.txt`

## fuel cms 1.4
