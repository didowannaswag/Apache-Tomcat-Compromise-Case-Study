# Attack Path

## Step 1 – Discovery
Nmap scan revealed port 8180 running Apache Tomcat.

## Step 2 – Enumeration
Gobuster scan revealed /manager page.

## Step 3 – Credential Attack
Used default credentials to authenticate.

## Step 4 – Exploitation
Uploaded WAR reverse shell via Tomcat Manager.

## Step 5 – Access
Obtained reverse shell as tomcat user.

## Step 6 – Privilege Escalation
Performed local enumeration and escalated to root.
