### KoTH Food CTF Notes

Target IP: 10.10.38.214

Apparently contains eight 'flags'

Enumeration:

nmap:

- `nmap -sV -sC 10.10.35.214`

only returned 3 open ports.

- 22 ssh
- mysql
- 9999 (abyss?)

Abyss appears to be something needed for the KoTH game, and most likely won't give any access

ssh requires a password/key, which we don't have.

Re-running nmap scanning for every available open port using `nmap -sV -sC -p- 10.10.38.214`

gobuster

Initially ran gobuster on 214:9999, as that was the first port I found that had http running. That was a deadend, as it had every possible directory return a 200 code.

Will rerun it if a different http port is found on the second nmap scan.



