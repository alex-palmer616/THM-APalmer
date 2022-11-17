### Overpass notes.

Target IP address: 10.10.81.101

Goals, `user.txt` and `root.txt`

Tags:
- `security`
- `owasp top 10`
- `easy`
- `cron`

### Enumeration


#### nmap

`nmap -sV -sC $IP`

- p 22
- p 80

#### gobuster

`gobuster dir -u http://$IP -w /usr/share/wordlists/common.txt`

/aboutus
/admin
/css
/downloads
/img
/index.html



#### website


/aboutus

- Little page of flavor text, but also has some useful info.
	- Possible usernames
		- Ninja
		- Pars
		- Szymex
		- Bee
		- MuirlandOracle
	- Mentions that the passwords are stored 'locally'
- Nothing in the page source that seems of use. 	


/admin

/css
- Basic .css files for login and main

/downloads
- Versions of the overpass 'software', both precompiled and a source code with script


/img
- contains 3 image files. A .jpg, .png and a .svg

/index.html
- Source contains reference to ROT13 for encryption.
- contains links to `about us` and `/downloads`

[{"name":"System","pass":"saydrawnlyingpicture"}]
