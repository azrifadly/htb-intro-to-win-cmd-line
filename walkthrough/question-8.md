# Question 8 – Domain Controller Authentication & PowerShell Modules

## Question
**Description:**  
For this level, you must successfully authenticate to the **Domain Controller** host at `172.16.5.155` via SSH after first authenticating to the target host. This host appears to have several PowerShell modules loaded, and the user's flag is hidden in one of them.

## Instructions:
- SSH into the target host  
- From the target host, SSH into the Domain Controller at `172.16.5.155`  
- Identify the available PowerShell modules  
- Search through the modules to find the hidden flag  
- Record the flag value  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question8-screenshot.png)

---
## Solution:
- SSH into the target host using the provided credentials  
- SSH into the Domain Controller:  
  ```powershell
  ssh user7@172.16.5.155
