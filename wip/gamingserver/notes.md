### Gaming Server Notes

Target IP 10.10.232.38

Goals:
- User flag
- root flag.

Room tags: `security` `lxd` `ssh2john` `boot2root`

##### enumeration

#### nmap

`nmap -sV -sC 10.10.232.38`

- 22
- 80 (apache 2.4.29)

#### gobuster	

`gobuster dir -u http://10.10.232.38 -w /usr/share/wordlists/dirb/common.txt`

- /index.html
- /robots.txt
- /secret
- /uploads

#### website

in the page source for `index.html` there is a note asking `john` to add actual content to the site, for a potential username

`robots.txt` only includes /uploads which we foun with gobuster.

`/uploads` contains a list of potental passwords, a manifesto of sorts, and `meme.jpg`. I will see if there is anything in meme with binwalk, and check the exif data.

`/secret` has a private key, which may be useful for ssh with john as a u
