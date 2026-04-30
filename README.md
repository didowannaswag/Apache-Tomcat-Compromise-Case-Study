# Apache Tomcat Compromise Case Study

##  Overview

This project demonstrates a full attack chain against an exposed Apache Tomcat server in a controlled lab environment.

---

##  Objectives

* Gain initial access
* Achieve remote code execution
* Escalate privileges
* Assess system impact

---

##  Lab Setup

* Kali Linux (attacker)
* Metasploitable2 (target)

---

##  Attack Chain

1. Nmap scan detected port 8180
2. Apache Tomcat detected
3. Found /manager 
4. Weak credentials used
5. WAR payload downloaded
6. Reverse shell obtained
7. Privilege escalation performed

 Details: `methodology/attack-path.md`

---

##  Key Findings

* Exposed Tomcat Manager
* Weak credentials
* WAR deployment → RCE
* Privilege escalation

---

##  Screenshots

See `/screenshots`

---

## Full Report

See `/report/final-report.md`
