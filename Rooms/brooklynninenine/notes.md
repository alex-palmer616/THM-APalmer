### brooklyn nine nine Notes

#### info

Target IP address: 10.10.200.250

Nmap
`nmap -sV -sC $IP`

![nmap](images/nmap.png)

ports
21 (anon FTP)
22 (ssh)
80 (http)

Gobuster

![gobuster](images/gobuster.png)

`gobuster dir -u http://10.10.200.250 -w /usr/share/wordlists/dirb/common.txt`

/index.html
/server-status

![homepage](images/homepage.png)

![pagesource](images/pagesource)

## FTP

`ftp $IP`

`get note_to_jake.txt`

![ftp](images/ftp.png)

![note](images/note.png)

## Steg

`stegcracker brooklyn99.jpg`
![stegcracker](images/stegcracker.png)
![steg note](images/stegnote.png)

##SSH

holt:fluffydog12@ninenine

![ssh](images/ssh.png)

![user](images/user.png)

