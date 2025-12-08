Netdiscover 

arpscan

Nmap

nikto

directory busting
	dirbuster 
	dirb
	gobuster
	ffuf

metasploit framework
	msfconsole
		search, use, show options, set, check (if vuln or not), run/exploit
	msfvenom

smbclient

searchsploit 

netcat
	reverse shell: victim connects, attacker listens
	bind shell: victim listens, attacker connects

paylods
	non-staged payload: sends payload all at once. 
		ex. windows/meterpreter_reverse_tcp
	staged payload: sends payload in stages.
		ex. windows/meterpreter/reverse_tcp

files:
	/etc/passwd: all users in it
	/etc/shadow: all users with password hashes in them

Hydra
	brute force for ssh, ftp, etc.
	can use msf as well

Nmap -A -p- -T4 <target IP>

hash-identifier
	hash type
	can crack using hashcat
		syntax: hashcat -m <mode> <hash value or hash file> <path to wordlist>
		example: hashcat -m 0 hashes.txt /usr/share/wordlists/rockyou.txt
			 -m is the mode and we're setting it for MD5 hash.

locate <filename> to find path of file

php reverse shell: https://github.com/pentestmonkey/php-reverse-shell
	upload php
	nc -nvlp <port> on attacker for reverse shell

linpeas
	host simple webserver 
		command: python3 -m http.server
	wget to get the file or certutil.exe 

	chmod +x <file>
	./script.sh

systemctl list-timers

pspy: https://github.com/DominicBreuker/pspy

https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

mouting shared
	showmount -e <IP address>
	mkdir /mnt/dev
	mount -t <type from showmount> <ip address>:/sv/nfs /mnt/dev

fcrackzip
	crack zip files
	example: fcrackzip -v -u -D -p <wordlist file> file.zip

sudo -l (to list)

gtfobins for escalation

dnsrecon -r 127.0.0.0/24 -n <target IP> -d <domain anything it requires to search>

TTY shell: https://wiki.zacheller.dev/pentest/privilege-escalation/spawning-a-tty-shell

binaries with permissions (SUID and SGID)

find / -type f -perm -4000 2>/dev/null
	to find all binaries 
