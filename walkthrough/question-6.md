# Question 6 – User Enumeration

## Question
**Description:**  
Determine how many user accounts exist on the host, **excluding** the `DefaultAccount` and `WDAGUtility` accounts.

## Instructions:
- SSH into the host with user5
- List all user accounts on the system  
- Exclude the `DefaultAccount` and `WDAGUtility` accounts from your count  
- Record the total number of remaining user accounts  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question6-screenshot.png)

---
## Solution:
- Use the `net user` command to list all user accounts  
- Manually exclude `DefaultAccount` and `WDAGUtility` from the list  
- Count the remaining users  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question6-solution.png)

- Answer: `14`
