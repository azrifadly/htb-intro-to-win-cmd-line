# Question 7 – Registered Owner

## Question
**Description:**  
For this level, you need to find the **Registered Owner** of the host. The Owner name is the flag.

## Instructions:
- SSH into the host  
- Locate the system information that contains the Registered Owner field  
- Record the value of the Registered Owner (this is the flag)  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question7-screenshot.png)

---
## Solution:
- Use the `systeminfo` command to display system details
- However, this prints alot of details to sift through

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question7-solution.png)
  
- So, we use `systeminfo | findstr "Registered Owner"` to filter through the chunk of system details
- Note the value displayed  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question7-solution1.png)

- Answer: `htb-student`
