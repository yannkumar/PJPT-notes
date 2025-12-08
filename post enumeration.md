ldapdomaindump
	usage: sudo ldapdomaindump ldaps://<domaincontrollerIP> -u 'username' -p 'password' -o <outputdir> 

bloodhound
	 we need to run neo4j to use bloodhound. Command: sudo neo4j console website at localhost:7474 and login creds is neo4j:neo4j.
	 
	 Then we run 'sudo bloodhound' with neo4j login as mentioned above. 
	
	 make a bloodhound dir to save files found.
	 
	  command: sudo bloodhound-python -d <domain> -u 'username' -p 'password' -ns <domain controller IP/Name server IP> -c all
	
	 then on right upload data > all files found in bloodhound dir > open.

Plumhound
	requirements: it should be running bloodhound first and setup with visuals.
	first test to see if it runs command: sudo python3 plumhound.py  --easy -p neo4j (neo4j pass) 
	
	usage: sudo python3 plumhound.py -x tasks/default.tasks -p neo4j

Pingcastle
	 Windows tool download.
	 