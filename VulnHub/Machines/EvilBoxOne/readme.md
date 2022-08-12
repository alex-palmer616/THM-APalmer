# Vulnhub - EvilBoxOne

## Intro

Hello and welcome to my walkthrough/write-up for the Vulnhub machine [EvilBoxOne](https://www.vulnhub.com/entry/evilbox-one,736/-).

Generally speaking, I create these and write them as I am working on the machine, and utilize this to take notes. Any place that a specific IP address is mentioned, that is the IP address what was assigned to the target machine by the DHCP server provided by the PFSense firewall that is enabled, and therefore will vary to what IP address your machine is mapped to. 

With that out of the way, let's get cracking. 



## Enumeration. 

To start off, I wanted to enumerate the machine with `nmap` to see what ports are open and what versions of services are running. The target machine was assigned 192.168.1.21 by PFSense

### nmap

For this part we can use the `nmap` command `nmap -sV -sC -p- -vv 192.168.1.21 -oA ~/Desktop...Evilnmap`

From that scan we can see that there are only two ports open, port 22(SSH) and port 80(HTTP).

### dirb

Because port 80 is open, I am going to jump the gun a bit and run a `dirb` scan against the target with `dirb http://192.168.1.21`

Once we run this we can see that there were 4 things found!

- http://192.168.1.21/index.html
- - Visiting this shows us an `Apache2 Debian Default Page`, which doesn't seem too useful for the time being. 

- http://192.168.1.21/robots.txt
- - This is always something to check out. This is a file that tells search engines to not index, and is often used in CTF's to show something is hidden. In this case we get a simple message of `Hello H4x0r` which doesn't seem useful for now, but we will keep it in mind. 

- http://192.168.1.21/secret
- http://192.168.1.21/secret/index.html
- - For right now, accessing both of these show a blank white page, with 5 empty lines viewing the page source. 

