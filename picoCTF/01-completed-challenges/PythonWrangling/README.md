# picoCTF-

## Intro

Welcome to a quick little writeup/walkthrough for the picoGym Practice Challenge: [Python Wrangling](https://play.picoctf.org/practice/challenge/166?page=1&solved=0) hosted on [picoCTF](https://picoctf.org)

While, most of these will be short guides, I'm sure that there will be some challenging ones that will go unfinished, and revisited in the future. 

I intend to (eventually) have all rooms that I've completed, indexed, and searchable by the tool/step taken to solve them to serve as a larger "guide"

Without further ado, let's begin. 

### Description/Tasks

"Python scripts are invoked kind of like programs in the Terminal... Can you run this Python script using this password to get the flag?"

## Solution

We are provided with three seperate files. `ende.py`, `pw.txt`, and `flag.txt.en`. Save those to a directory, and then navigate to that directory within your terminal. 

If you aren't familiar with how to run python scripts, it would be a good idea to read the manpage for python by using `man python`. Doing so will also give us a good idea on how to utilize the other files that we were given besides the script file. 

If we just run the script using `python ende.py` we get an output of `Usage: ende.py (-e/-d) [file]`. With that output it looks like the `-e` flag might encrypt a file, while `-d` decrypts. Running `python ende.py -d pw.txt.en` prompts us for a password. 

If we view the contents of `pw.txt` with `cat pw.txt` we get a string of characters. Select and copy that string, and paste it when prompted for the password, and the flag will be revealed!
