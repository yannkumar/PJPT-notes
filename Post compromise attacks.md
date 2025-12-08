Pass the hash
	crackmapexec 
		usage: crackmapexec smb <IP range> -u <username> -d <domain>  -p <password> 
		To dump sam: --local-auth --sam 
		To get shares: --local-auth --shares
		We can check the list of everything using cmedb.