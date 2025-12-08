
***Reconnaissance (Recon)***
	- Process of gathering information about the target to use in the future. Basically a preparation phase. Depends on the type of testing done if it is internal pentest then you'll skip this step. 
	- **Two types of Recon:**
		- Active: Getting info directly by interacting with our target using tools to scan or other methods.
		- Passive: Getting info about target by using methods such as social media, news articles, etc.

***Scanning with enumeration (Scans)***
	- Running Scans with tools or performing vulnerability scans to get a map of the network with vulnerable services or open ports which can be used to map our the network and attack surface.

***Gaining Access***
	- This is where we exploit found vulnerabilities by using tools to gain access to machines or to the network. After that the attacker can either move onto lateral movement or privilege escalation. 

***Maintaining Access***
	- Now that we have access to the network or machine we should create a way in which we can maintain this connection by installing rootkits or other means to keep the connection alive or persistent.

***Clearing Tracks (Cleanup)***
	- After the attack and gaining whatever we wanted, we make sure they never find our we were in their network so we either clear logs or modify the logs, delete any app we installed, etc. We do that in order to clear our tracks.


