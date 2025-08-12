# Question 11 – Brute Force Logon Failures

## Question
**Description:**  
Identify the **user account** on the Domain Controller that has many Event ID **4625** logon failures generated in rapid succession, which is indicative of a **password brute force attack**.
The flag is the name of the user account.

## Instructions:
- SSH into the Domain Controller  
- Review the Security event logs for Event ID `4625` (failed logon attempts)  
- Identify the account with many such events in a short time frame  
- Record the username as the flag  

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question11-screenshot.png)

---
## Solution:
- Launch PowerShell on the Domain Controller  
- Use the `Get-WinEvent` command to filter Security logs for Event ID 4625:

  ```powershell
  Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625}

- This is a problem as it prints alot of 4625 event logs, and we need to identify the account with many of such events

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question11-solution.png)

- Let's pipe it down further with the "For" loop

  ```powershell
  Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625} | ForEach-Object { $_.Properties[5].Value } | Group-Object | Sort-Object Count -Descending

![image alt](https://github.com/azrifadly/htb-intro-to-win-cmd-line/blob/main/screenshots/question11-solution1.png)

- Command Breakdown:

1) `Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625}`

- This retrieves all events from the Security event log where the Event ID is 4625.
- Event ID 4625 corresponds to failed logon attempts (logon failure events).
- Using -FilterHashtable is efficient because it filters events on the system level rather than getting everything and filtering after.

2) `ForEach-Object { $_.Properties[5].Value }`
  
- For each event retrieved, this accesses the 6th property (Properties is zero-indexed) of the event.
- Specifically, .Properties[5].Value holds the TargetUserName (the username for whom the failed logon was attempted).
- So this step extracts the username from each failed logon event.

3) `Group-Object`
- Groups all identical usernames together.

4) `Sort-Object Count -Descending`
- Sorts the grouped usernames by the count of occurrences, in descending order. The user with the most failed login attempts appears at the top.

- Answer: `justalocaladmin`
