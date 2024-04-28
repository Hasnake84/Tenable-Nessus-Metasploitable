<a href="https://imgur.com/NuMXYAd"><img src="https://i.imgur.com//NuMXYAd.png" title="source: imgur.com" /></a> 

Note: This project is intended for educational purposes only. It's crucial to obtain permission before scanning any system other than your own.

# Tenable-Nessus 
Vulnerability Assessment and Remediation on Metasploitable Machine using Tenable Nessus on Windows VM
This project aims to identify and address security vulnerabilities on a Metasploitable machine using Tenable Nessus vulnerability scanner installed on a Windows virtual machine (VM).

# Objectives:
# 1. Install Tenable Nessus on a Windows VM.
- Configure a Windows and Metasploitable VM on a hypervisor (VirtualBox)
- Download Tenable Nessus on the Windows VM from  https://www.tenable.com/downloads/nessus
- Compare and verify SHA256 value fingerprint for file integrity, from the downloaded file to tenable.com/downloads/nessus

 <a href="https://imgur.com/KFSPLGu"><img src="https://i.imgur.com//KFSPLGu.png" title="source: imgur.com" /></a>
 <a href="https://imgur.com/Y6baJYz"><img src="https://i.imgur.com//Y6baJYz.png" title="source: imgur.com" /></a>

# 2. Configure Network Access for Scanning:
- Ensure network connectivity between the Nessus VM and the Metasploitable machine.
- Have Windows vm with Nessus and Metasploitable machine in the same VLAN subnet.
  
 <a href="https://imgur.com/A3gxoxZ"><img src="https://i.imgur.com//A3gxoxZ.png" title="source: imgur.com" /></a> 

# 3. Create and Run a Vulnerability Scan on Metasploitable:
- Design a Nessus scan template targeting the Metasploitable operating system.
  - Host discovery scan
  - Network scan
  - Advanced scan
- Execute the vulnerability scan on the Metasploitable machine.
  
 <a href="https://imgur.com/fEeYCpl"><img src="https://i.imgur.com//fEeYCpl.png" title="source: imgur.com" /></a> 
 
Analyze the generated Nessus scan report for identified vulnerabilities.
Remediation of Identified Vulnerabilities.
Prioritize vulnerabilities based on severity and exploitability.

 <a href="https://imgur.com/YrH6fae"><img src="https://i.imgur.com//YrH6fae.png" title="source: imgur.com" /></a> 
 <a href="https://imgur.com/HP2yjta"><img src="https://i.imgur.com//HP2yjta.png" title="source: imgur.com" /></a> 

From the generated report, which has 32 Critical and 95 High and 135 Medium vulnerabilities, have select a few from the criticals and outlined a remediation action plan.

# Remediation action plan and recommendations
- Apache log4j 1.x: Update to the latest log4j version (log4j 2.x) that addresses these vulnerabilities.
- Bash Remote Code Excution (Shellshock): Host is running a version of Bash that is vulnerable to command injection via enviroment variable manipulation, update Bash to remediate.
- Bash shell backdoor: A shell is listening on the remote port without any authentication being required. An attacker may use it by connecting to the remote port and sending commands 
  directly, Consider resetting passwords and rebuilding affected systems if necessary.
- Weak SSH keys: Revoke weak keys and regenerate strong unique keys for SSH access.
- VNC server "password" password: Change the VNC server password to a strong, unique passphrase.
- Apache Tomcat AJP: Update Tomcat to a version that addresses the Ghostcat vulnerability, also disable the AJP connector if not in use.
- SSLv2/v3: Disable SSLv2 and SSLv3 protocols on host and implement TLS v1.2 or higher for secure connections.
- OpenSSH/OpenSSL RNG weakness: Update the OpenSSH and OpenSSL packages to address the random number generator weakness. 
- Unsupported OS: Upgrade the unsupported operating systems to a supported version to receive critical security patches and fixes. 
- NFS share disclosure: Review and adjust NFS export permissions to restrict access to sensitive information. Only export necessary data and limit access to authorized users or systems.

This project provides a structured approach to identify and address security weaknesses on a vulnerable machine. By successfully completing this project, i have gained a practical experience with Tenable Nessus, vulnerability scanning methodologies, and basic vulnerability remediation techniques.
 <a href="https://imgur.com/lR9xxw7"><img src="https://i.imgur.com//lR9xxw7.png" title="source: imgur.com" /></a> 




