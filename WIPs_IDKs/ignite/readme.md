# Ignite

Hello, and welcome to my walkthrough/write-up for the [TryHackMe](https://TryHackMe.com) room [Ignite](https://tryhackme.com/room/ignite)

One thing I want to note ahead of time with this room, is that I ended up spending a lot of time looking in the wrong places in this machine. And while this will have all of the steps that are required to complete this room, I will also be making note of the areas I got lost in, and what I learned from those specifically. 

The only other thing that I wanted to note, is that anytime that `$IP` is used in a command, it is represents the target machines IP address. 

With that out of the way, lets begin!

## Enumeration

As the first step we should always take is to begin scanning the target to find possible attack vectors. 

We can do that with a few different tools. The two we will use are `nmap` and `gobuster`.


### nmap

We can run a `nmap` scan against the target using the following command:

`nmap -sV -sC $IP`

As you can see in the image below, we see that the only port that is open is port 80 (http). There is also a mention that a `robots.txt` that exists preventing the `/fuel/` directory from appearing in various search results. That is something that we should take note of. 

### gobuster

`gobuster` is a tool that will show us the directories that exist, even if there isn't a direct link to them. We can run it against the target with the following command:

`gobuster dir -u http://$IP -w /usr/share/wordlists/dirb/common.txt`

In the results show below, we can see that there are a handfull of directories and files that appear. Again the `robots.txt` appears.

![gobuster](images/gobuster.png) 

### The target itself.

Since we saw that port 80 was open when we ran the `nmap` scan, that generally means that there is a website hosted on this machine that _should_ be accessible via a web browser. 

Opening the target `$IP` in a web browser shows the following:

This seems like it is a website















