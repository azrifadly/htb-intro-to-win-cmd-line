# Question 10 – VM Process Name

## Question
**Description:**  
Use the `tasklist` command to print running processes and then sort them in **reverse order by name**. The name of the process that begins with `"vm"` is the flag for this user.

## Instructions:
- SSH into the target host  
- Run `tasklist` to display all running processes  
- Sort the process list in **reverse alphabetical order** by name  
- Locate the process that begins with `"vm"`  
- Record the process name as the flag  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question10-screenshot.png)

---
## Solution:
- Run `tasklist` and pipe it into `sort` with the `/R` flag to reverse the order:  
  ```powershell
  tasklist | sort /R
  
![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question10-solution.png)

**OR**

- Run `tasklist` and pipe it into `findstr "vm"` to find string that begins with vm then pipe it again into `sort` with the `/R` flag to reverse the order:  
  ```powershell
  tasklist | findstr "vm" sort /R

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question10-solution1.png)
