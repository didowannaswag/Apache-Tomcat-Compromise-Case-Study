# Attack Path

## Step 1 – Discovery
Nmap scan revealed port 8180 running Apache Tomcat.

## Step 2 – Enumeration
Gobuster scan revealed /manager page.

## Step 3 – Credential Attack
Create users wordlist with default credentials and also password wordlist for brute force. Used Hydra for brute force HTTP Basic Authentication login page in /manager.

## Step 4 – Exploitation
After gaining access to the manager page: A reverse shell war file was generated using Metasploit(The options were set up). The WAR reverse shell was uploaded via Tomcat Manager.

## Step 5 – Access
A listener was created and a shell file was opened. A reverse shell was obtained as the Tomcat user.

## Step 6 – Privilege Escalation
Performed local enumeration and escalated to root.
