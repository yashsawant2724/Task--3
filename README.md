# Task-3

Objective: Use free tools to identify common vulnerabilities on your computer.

Tools: OpenVAS Community Edition (free vulnerability scanner).
 
Deliverables: Vulnerability scan report with identified issues.

**Step 1: Installing OpenVAS**
manually download and install the new key
sudo wget https://archive.kali.org/archive-keyring.gpg -O /usr/share/keyrings/kali-archive-keyring.gpg

Updated system packages:
sudo apt update && sudo apt upgrade

![image](https://github.com/user-attachments/assets/3cb5a30d-fec5-413e-9773-d1913b120a33)


Installed OpenVAS and dependencies:
sudo apt install openvas

![image](https://github.com/user-attachments/assets/a1700af2-e71a-4df6-b8ac-76b5fc467339)

Faced too many errors while installing openvas as shown in screenshot below

![image](https://github.com/user-attachments/assets/592e3657-defc-436a-b034-4be106ba0153)
![image](https://github.com/user-attachments/assets/7dc68878-857e-4bee-956d-e130767fdd20)

Took me awhile but running below commands solver the issue
sudo apt-get install kali-desktop-core

![image](https://github.com/user-attachments/assets/d3288eea-0c26-4b00-a61a-58816a4d2559)
![image](https://github.com/user-attachments/assets/afba0940-1a8a-4076-858e-021f3751eadf)

Ran initial setup:
sudo gvm-setup
This configured the database, services, and fetched vulnerability data.
This installation process took along time about 30-45 mins.

![image](https://github.com/user-attachments/assets/be5c2ec2-d058-41a1-a8c3-d1f6be80e1e1)


Checked the installation:
sudo gvm-check-setup

**Step 2: Setting Up Scan Target**
Logged into the Greenbone Security Assistant web UI at https://localhost:9392.
Navigated to Configuration → Targets → New Target.
Filled in the following:
Name: "Localhost Vulnerability Test"
Host: 127.0.0.1
Port List: All TCP and UDP (default)
Saved the target.

**Step 3: Launching a Full Vulnerability Scan**
Navigated to Scans → Tasks → New Task.
Provided task details:
Name: "Full Localhost Scan"
Scan Config: Full and Fast
Target: Localhost (created earlier)
Started the scan by clicking Start Task.

**Step 4: Wait for Scan to Complete**
Duration: Approximately 45–60 minutes
Scanner performed the following checks:
Port scanning (TCP/UDP)
Service enumeration
Banner grabbing
CVE checking based on plugin database
Verified progress from dashboard.

**Step 5: Review the Report for Vulnerabilities**
After completion:

Opened the Scan Results Report.
Observed vulnerabilities classified into categories:
Critical
High
Medium
Low
Informational

Each vulnerability listed:
Plugin Name
CVE ID
Risk Factor
Description
Solution
Affected Ports and Services

**Step 6: Research Simple Fixes or Mitigations**
For top vulnerabilities (Critical/High):

Common mitigation techniques:
Patching outdated software
Disabling insecure protocols (e.g., SMBv1)
Updating misconfigured services
Changing default passwords
Disabling unused ports/services

**Results Summary**
Total Vulnerabilities Found: 18
Critical: 2
High: 5
Medium: 6
Low: 3
Informational: 2

**Conclusion**
This project has been instrumental in bridging theoretical knowledge of cybersecurity with practical hands-on experience. I now understand how to identify and prioritize vulnerabilities in real systems and how crucial vulnerability management is to maintaining secure IT infrastructure.
