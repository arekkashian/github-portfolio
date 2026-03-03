# Lab 02: System Audit
**Date:** February 2026  
**Status:** Completed  

## Section 1: System Inventory
| Component        |                                          |
|------------------|------------------------------------------|
| Operating System | Windows 11 Version 24H2 Build 26100.7623 |
| CPU              | AMD Ryzen 7 PRO 8840HS                   |
| Memory           | 32 GB                                    |
| Storage          | Kioxia SSD 950 GB                        |

## Section 2: Access Control Model
Microsoft [describes](https://learn.microsoft.com/en-us/windows-server/identity/solution-guides/dynamic-access-control-overview) Windows 11 access control model as Dynamic Access Control, this means that resource owners control permissions.

The Principle of Least Privilege is shown by that when a user opens a command prompt in Windows 11, they by default open it without administrator permissions, and you have to choose to open the prompt or any other program as an administrator specifically to access that permission level

On my system, looking around the system32 directory, many of the DLLs there are read-only for regular users and for administrators as well, which also demonstrates this principle

## Section 3: Process Analysis
1. PID 25972 - Notepad++ - This is a text editor and could be attacked, and has in fact been attacked, by the servers providing the updates to the program being compromised to install malware through the update system. This could irritate the user, or it could piggyback off escalated priviliges given to the notepad++ program. It could perhaps be used for data exfiltration as well, as it could communicate whatever is being edited back to a remote server
2. PID 27028 - Firefox - This is a web browser and it could be attacked in the same way as Notepad++ was. The consequences could be the theft of passwords or login information from the web browser, or others
3. PID 1928 - Winlogon - This is part of the operating system that logs users in, it could be replaced by a malicious version that allowed privilege escalation
