## chill hack notes

## Info

Room name: [Chill Hack](https://tryhackme.com/room/chillhack)
Room Tags:
- `security`
- `realworld`
- `commandinjection`
- `sqlinjection`

Target IP: `10.10.186.114`

## Enumeration

nmap:
`nmap -sV -sC 10.10.186.114 -oA chillhack`

- 21 (anonFTP)
- 22 (ftp)
- 80 (http)

gobuster:

`gobuster dir -u http://10.10.186.114 -w /usr/share/wordlists/dirb/common.txt`

/css
/fonts
/images
/index.html
/js
/secret
/server-status

gobuster2:
`gobuster dir -u http://10.10.186.114/secret -w /usr/share/wordlists/dirb/common.txt`


