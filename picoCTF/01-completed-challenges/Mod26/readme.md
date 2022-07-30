# picoCTF-

## Intro

Welcome to a quick little writeup/walkthrough for the picoGym Practice Challenge: [Mod 26](https://play.picoctf.org/practice/challenge/144?page=1&solved=0) hosted on [picoCTF](https://picoctf.org)

While, most of these will be short guides, I'm sure that there will be some challenging ones that will go unfinished. 

I intend to (eventually) have all rooms that I've completed, indexed, and searchable by the tool/step taken to solve them to serve as a larger "guide"

Without further ado, let's begin. 

### Description/Tasks

Cryptography can be easy, do you know what ROT13 is? cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}

## Process

In the description it asks us if we know what ROT13 is. ROT13 is also known as the 'Ceasar Cipher' where each character in the plain-text that is going to be encrypted is shifted 13 places. I.E A = N, B = O, and Z = M. As we are given the flag, but it is obviously encrypted, we need to apply a decoder to get it back in to plain, useable, text. 

## Solution

One of the most useful tools that you should have bookmarked is [CyberChef](https://gchq.github.io/CyberChef).

If we visit that site, we can see a `input` and an `output` on the right hand side. We can copy/paste the encrypted flag into the input text box, and then select a `recipe` on the left hand side. You can either enter `ROT13` into the search bar, or select it by going to Encryption/Encoding and double-clicking on `ROT13`. You should then see the decoded flag in the `output` window
