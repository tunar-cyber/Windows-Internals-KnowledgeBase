# Windows Access Tokens

## Overview
An Access Token is a kernel-managed security object representing the security context of an authenticated user or service. Windows creates it immediately after successful authentication and uses it to make authorization decisions throughout the user's session.

## Why Windows Needs Access Tokens
Windows does not consistently ask Active Directory or the SAM database.
It authenticates a user only once during logon.
After authentication succeeds, Windows no longer repeatedly verifies the user's password against Active Directory or the SAM database.
Instead, authorization decisions are made using the Access Token that LSASS created during logon.


## Access Token Creation
1. User enters credentials.

2. Winlogon forwards the request.

3. LSASS receives it.

4. LSASS invokes Kerberos or NTLM.

5. Credentials are verified.

6. LSASS creates the Access Token.

7. Explorer.exe receives the primary token.

8. Child processes inherit copies.




## What Does an Access Token Contain?
User SID - Identifies the authenticated user
Group SIDs - Membership of security groups 
Privileges - System Privileges 
Integrity Level - Determines the process Trust level
Default DACL - Default permissions for newly created objects. 

## How Windows Uses Access Tokens
Let's use analogy. Suppose Alice wants to open a excel file called "salary.xlsx". 
Windows perform an access check: 
<img>
The file has an Access Control List (ACL). An ACL is a list of rules specifying which SIDs can access an object and what operations they are allowed or denied. 


## Primary vs Impersonation Tokens
Primary token: 
Every process has one primary token. Ex: Explorer.exe , Powershell.exe, Chrome.exe. Each runs using its primary token. 
Impersonation token :
A thread can temporarily act as another identity. A file server receives a request from Alice. The server process runs as : SYSTEM. 
<diagram>

## Token Inheritance
This explains why every application know who you are. When Explorer starts , it gets your token. Later:  Explorer —> Powershell —> CMD —> Notepad. All inherit copies of the parent’s primary token. This inheritance is why opening CMD does not require you to authenticate again. 


## References
