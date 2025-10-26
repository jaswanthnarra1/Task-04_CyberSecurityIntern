# Task-04_CyberSecurityIntern
 TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux
🎯 Overview:
This project demonstrates how to configure and test firewall rules on Kali Linux using UFW (Uncomplicated Firewall).

📝 Step-by-Step Procedure:
Linux:
Enable Firewall
Activated UFW to start filtering network traffic:

sudo ufw enable


List Current Rules
Displayed existing rules with:

sudo ufw status numbered
Output showed SSH (22/tcp) allowed and Telnet (23/tcp) denied.


Block Telnet (Port 23)
Added a deny rule:

sudo ufw deny 23/tcp
Confirmed with sudo ufw status numbered.


Test the Rule
Verified Telnet was blocked using Telnet and Netcat:

telnet localhost 23
nc -vz localhost 23
Both returned Connection refused.


Allow SSH (Port 22)
Ensured SSH remained accessible:

sudo ufw allow 22/tcp
Verified in ufw status.

Remove Test Rule (Telnet Block)
Deleted the Telnet deny rule to restore the firewall state:

sudo ufw delete deny 23/tcp
Final rules allowed only SSH (22/tcp).

✅Commands Used
sudo ufw enable
sudo ufw status numbered
sudo ufw deny 23/tcp
telnet localhost 23
nc -vz localhost 23
sudo ufw allow 22/tcp
sudo ufw delete deny 23/tcp
🚨 Firewall Summary
A firewall acts as a security filter between a system and external traffic.

Allow rules permit safe traffic (e.g., SSH on port 22).
Deny rules block unsafe or unused services (e.g., Telnet on port 23).
By configuring firewall rules, we minimize exposure to attacks and ensure only authorized connections are allowed.
Windows 11:
🧰 Tool: Windows Defender Firewall (GUI-based interface)
Open Windows Firewall Settings: Navigated to: Control Panel → System and Security → Windows Defender Firewall Clicked on 'Advanced Settings' from the left panel to access advanced rule configuration.

View Current Firewall Rules: Selected 'Inbound Rules' to view existing traffic rules. Observed default rules for applications and system services.

Create Rule to Block Inbound Traffic on Port 23 (Telnet): • Clicked 'New Rule' in Inbound Rules. • Selected 'Port' as the rule type. • Chose 'TCP', specified port 23. • Action: Block the connection. • Applied rule to: Domain, Private, Public. • Gave it a name: Telnet.

Test the Block Rule: Opened Command Prompt and attempted to connect using: telnet localhost 23

📸 Screenshot:

image alt

image alt



📝 Purpose:
Port 23 is used by the insecure Telnet protocol. Blocking it prevents potential unauthorized access.
