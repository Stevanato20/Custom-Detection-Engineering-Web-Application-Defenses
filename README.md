# Custom-Detection-Engineering-Web-Application-Defenses
Customizing XML-based Wazuh detection rules to trigger high-priority alerts for web directory brute-force attacks and scanner user-agent signatures.

Architecture & Tools Used:
-Virtualization: Oracle VirtualBox
-Target Web Server: Ubuntu Server 
-Attacker: Kali Linux
-SIEM / Log Analysis Wazuh Dashboard / Wazuh Manager

Lab Objectives:

-Deploy an Nginx web server on Ubuntu and configure log ingestion into Wazuh.

-Launch directory brute-forcing and vulnerability scanning tools like 'gobuster', 'dirb', and 'nikito' from Kali Linux.

-Analyze raw Nginx access logs at '/var/log/nginx/access.log'.

-Engineer a custom Wazuh XML detection rule ('local_rule.xml') to generate High-Security (Level 10+) alerts upon detecting rapid '404' error frequencies and scanner signatures.


Rule creation:

-The rule Id 10004 Level 10 was created using XML as shown on the picture below.

<img width="973" height="427" alt="image" src="https://github.com/user-attachments/assets/41087fbe-3301-41e2-a7bf-05acd99d7811" />


Attack Execution:

-Using Gobuster, a brute-force attack was perfomed against the ubuntu machine ip (192.168.0.96) using the following command ( gobuster dir -u http://192.168.0.96 -w /usr/share/wordlists/dirb/common.txt.

<img width="975" height="447" alt="image" src="https://github.com/user-attachments/assets/e7a6ae8a-dd6e-4390-9daf-b77d522efc83" />
<img width="973" height="592" alt="image" src="https://github.com/user-attachments/assets/a0392c41-3e98-4b65-b503-16b9fb9a687f" />

Verification & Results:

-The attack perfomed was visible on Wazuh as well as the rule number 10 as shown on the picture below.

<img width="973" height="394" alt="image" src="https://github.com/user-attachments/assets/038f70d7-4650-4d25-a67f-405d34b110e7" />
<img width="882" height="642" alt="image" src="https://github.com/user-attachments/assets/81155fc5-afe5-4cbc-902e-2e5f19cd821d" />


