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
This installation process took along time about 45-60 mins.

![image](https://github.com/user-attachments/assets/be5c2ec2-d058-41a1-a8c3-d1f6be80e1e1)

Faced an error needed to alter database version

![image](https://github.com/user-attachments/assets/c41ce6f4-7d9b-4fec-99a9-9b5a291d45f8)


Checked the installation:
sudo gvm-check-setup
![image](https://github.com/user-attachments/assets/d412cd7e-cc28-4dcf-813f-a4232a09fd24)

Launched the openvas
sudo gvm-start
![image](https://github.com/user-attachments/assets/45d5e774-97a3-4981-8e60-05e960b0b910)


**Step 2: Setting Up Scan Target**
Logged into the Greenbone Security Assistant web UI at https://localhost:9392.
Navigated to Configuration → Targets → New Target.
Filled in the following:
Name: "Localhost Vulnerability Test"
Host: 127.0.0.1
Port List: All TCP and UDP (default)
Saved the target.
![image](https://github.com/user-attachments/assets/fe0b87fd-47d6-46c1-925d-7acb3b7c1a0a)


**Step 3: Launching a Full Vulnerability Scan**
Navigated to Scans → Tasks → New Task.
Provided task details:
Name: "Full Localhost Scan"
Scan Config: Full and Fast
Target: Localhost (created earlier)
Started the scan by clicking Start Task.
![image](https://github.com/user-attachments/assets/068c405f-aaa1-4356-9318-4b6d0e7a3adc)


**Step 4: Wait for Scan to Complete**
Duration: Approximately 45–60 minutes
Scanner performed the following checks:
Port scanning (TCP/UDP)
Service enumeration
Banner grabbing
CVE checking based on plugin database
Verified progress from dashboard.

**Step 5: Reviewing the Report**
Once complete, clicked on the task to open the Report.
Observed a color-coded summary:
Red: Critical vulnerabilities
Orange: High
Yellow: Medium
Green: Low
Blue: Log/Info


**Conclusion**
This project has been instrumental in bridging theoretical knowledge of cybersecurity with practical hands-on experience. I now understand how to identify and prioritize vulnerabilities in real systems and how crucial vulnerability management is to maintaining secure IT infrastructure.
