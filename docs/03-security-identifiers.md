# Security Identifiers (SIDs)

## Overview

Security identifiers is the way in all Operating Systems how every file,process,users,threats, accounts and objects are uniquely 
identified. The core concept behind this idea is to prevent possible corruption in processes,authentication , authorization
and other important processes occuring inside OS. Each time when user logs in to account , the session is created and this session contains SIDs,
User rights and other important features belonging to user. 

## SID vs Username
there is a big difference between SID and usernames. Despite the both identifies and authenticates a user, SID is unique , while username can be vary and can contain upper,lower-case letters.
For this reason, in low-level operations, IT administrators and security engineers prefer to work with SIDs in order to not confuse a user, process, or generally , an object. 


## Common Well-Known SIDs

S-1-5-113 	Local account
S-1-5-2    	Network
S-1-5-6 	Service
S-1-5-11 	Authenticated Users 
S-1-5-19 	NT Authority (LocalService)
S-1-5-domain-512 	Domain Admins
S-1-5-domain-514 	Domain Guests

## Defender's Perspective

## Hands-on Observation
![whoami user](../screenshots/whoami-user.png)
The command displays both the current username and its associated Security Identifier (SID). While usernames are intended for human readability, Windows internally relies on the SID to uniquely identify the account.
