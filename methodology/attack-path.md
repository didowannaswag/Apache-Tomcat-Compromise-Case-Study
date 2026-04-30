# Attack Path

## Step 1 – Discovery
An Nmap scan identified an open port 8180 running an Apache Tomcat service on the target system.

## Step 2 – Enumeration
Directory enumeration using Gobuster revealed the `/manager` endpoint, indicating that the Tomcat Manager interface was publicly accessible.

## Step 3 – Credential Attack
Default and weak credentials were tested against the Tomcat Manager login interface.  
Custom username and password wordlists were created based on commonly used Tomcat credentials.  
Hydra was used to perform an HTTP Basic Authentication brute-force attack, which resulted in valid credentials.

## Step 4 – Exploitation
After successful authentication, access to the Tomcat Manager interface allowed deployment of applications.  
A malicious WAR file containing a reverse shell payload was generated using msfvenom and uploaded through the Manager interface.

## Step 5 – Access
A Netcat listener was configured on the attacker machine.  
Once the deployed application was triggered, a reverse shell connection was established, providing command execution as the Tomcat service user.

## Step 6 – Privilege Escalation
Local enumeration was performed to identify potential privilege escalation vectors.  
SUID binaries were discovered using the following command:

    find / -perm -4000 2>/dev/null

Further analysis revealed a misconfiguration that allowed privilege escalation using a known technique referenced from GTFOBins.  
This resulted in root-level access to the system.

---

## Attack Summary

Initial access was obtained through weak credentials on the exposed Tomcat Manager interface.  
This allowed deployment of a malicious application, leading to remote code execution.  
Privilege escalation was achieved via misconfigured SUID binaries, resulting in full system compromise.
