
# Authentication vs Authorization


## What is Authentication?
Authentication is the process of verifying the identity claimed by a user, device, or service using one or more credentials. For instance, when you try to login for a system , firstly you are required to perform entering your login credentials such as email, username, password and etcetera. This verifies you are eligible to use the system.

## What is Authorization?
Authorization is the process of determining which resources and actions an authenticated identity is permitted to access or perform. Depending on the access level, either you are allowed to use Windows Powershell or not. In organizations, this is generally configured by IT administrators. 

## Why Blue Team Analysts Must Understand the Difference
Understanding the difference allows security analysts to correctly interpret authentication failures, privilege escalation attempts, and suspicious login activity during incident investigations.

Example:

- Event ID 4625 → Authentication failed.
- "Access Denied" after login → Authorization failed.
## Hands-on Observation
