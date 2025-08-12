# Question 5 – Documents Folder Search

## Question
**Description:**  
User4 has a lot of files and folders in their Documents folder. The flag can be found within one of them.

## Instructions:
- SSH into the host as user4
- Navigate to user4's Documents directory
- Search through files and folders to find the flag
- Record the flag found

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question5-screenshot.png)

---

## Solution:
- SSH into the host as user4 using the flag from Question 4 as password
- Navigate to Documents directory using `cd Documents`
- Use `dir /s flag.txt` and found out there are many flag.txt with no bytes in them

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question5-solution.png)
  
- Using powershell, `Get-ChildItem -Recurse *.txt | Where-Object {$_.Length -gt 0}`
  
  <br>I am using the powershell version of dir for `Get-ChildItem`
  <br>`-Recurse` to search through all sub directories
  <br>`flag.txt` = because i know that the flag has this naming convention
  <br>now I pipe `|` the output to pass it to another command
  <br>`where-object` works like a filter
  <br>`$_` represents for each file
  <br>`.length` is the property for getting the size of a file in bytes
  <br>`-gt 0` is just greater than zero
  
- `cd C:\Users\user4\Documents\3\4` Change to the given directory where the flag.txt resides
- `cat flag.txt` show contents of the flag.txt

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question5-solution1.png)

- Answer: `Digging in The nest`
