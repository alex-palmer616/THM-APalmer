## Lian-Yu notes

Target IP: 10.10.37.246

nmap-
- `nmap -sC -sV 10.10.37.246`

- 21 (ftp)
- 22 (ssh)
- 80 (http-apache)
- 111 (rpcbind 2-4)

gobuster:
`gobuster dir -u http://10.10.37.246 -w /usr/share/wordlists/dirb/common(small).txt`
- /index.html
- /server-status

I had to play around with the wordlists untill I was able to find out that when ran returned the following directory:

/island

That mentioned a 'codeword' of `vigilante`.

I tried both `$IP/vigilante` and `$IP/island/vigilante` to no avail, so I decided to re-run gobuster on the island directory

re-running another gobuster scan on `$IP/island` gave us another directory, `2100`.

going to `$IP/island/2100` has some flavor text included, and in the page source mentions .ticket is here.

Running gobuster again against `$IP/island/2100` and looking for the .ticket extention eventually gives us `green-arrow.ticket


89 50 4E 47 0D 0A.
