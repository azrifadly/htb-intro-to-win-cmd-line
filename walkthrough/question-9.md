# Question 9 – GivenName of Domain User

## Question
**Description:**  
This flag is the **GivenName** of a domain user with the **Surname** "Flag".

## Instructions:
- SSH into the target host  
- Query the domain user accounts to find one with the **Surname** equal to "Flag"  
- Identify the user's **GivenName**  
- Record the GivenName as the flag  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question9-screenshot.png)

---
## Solution:
- Launch PowerShell on the host  
- Use the Active Directory module to search for the user:  
  ```powershell
  Get-ADUser -Filter { Surname -eq "Flag" }

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question9-solution.png)

- Answer: `Rick`
