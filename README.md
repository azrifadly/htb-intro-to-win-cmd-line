# Windows Host Credential Hunting – Lab Scenario
Skill Assessment for Intro To Windows Command Line

## Scenario
During a penetration test with our team, we were instructed to collect some information for a **non-critical Windows host**.  
Our team had recently gained access to this host, which contains many users.  
To allow the rest of the team to focus on more complex tasks, we were asked to take a closer look at this host.

**Primary Objective:**  
Find **usernames** and **passwords** for all users, enabling us to examine the system and document all credentials.

---

## Challenge Structure
- Each question corresponds to **one user account**.  
- You must authenticate as the correct user to complete that stage.  
- Tasks may involve:
  - Running **specific executables**  
  - Performing **specific actions**  
  - Locating information on the host to retrieve a **flag** for that stage

---

## Flag & Access Flow
- The **flag** for the current user will serve as the **SSH password** for the **next user**.  
  Example:  - This continues sequentially until the final user is reached.

---

## Exploration
If desired:
- Experiment with **multiple methods** to achieve the same result for each question.
- Compare one-liners, scripts, and tool usage.
- Document all approaches, even if only one is used for the final flag retrieval.

---

## Documentation Tips
When documenting:
- Include **one-liners** used for quick output.
- Add any **custom scripts**.
- Record the **exact commands** run and their output.
- Note **alternative approaches** discovered.

---

## Disclaimer
This scenario was executed in a **controlled lab environment** for **educational and ethical purposes only**.  
Do not attempt these techniques on any system without **explicit permission**.

---

