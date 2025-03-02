# Active Directory Homelab Setup 🚀

## Overview
This homelab demonstrates my experience setting up an Active Directory environment on Windows Server 2022.

## Components
- Windows Server 2022 (Domain Controller)
- Windows 10 VM (Domain-joined client)
- VirtualBox as the hypervisor

## Steps Taken
1. Installed Windows Server 2022 and configured Active Directory Domain Services (AD DS).
2. Created a domain (e.g., lab.local).
3. Added a Windows 10 VM and joined it to the domain.
4. Created and managed users, groups, and permissions.
5. Verified setup using PowerShell and Active Directory Users & Computers (ADUC).

## Verification Screenshots
![ADUC Screenshot](screenshots/aduc.png)
![Domain-Joined Client](screenshots/client.png)

## PowerShell Commands Used
```powershell
# List all domain-joined computers
Get-ADComputer -Filter * | Select Name, OperatingSystem

# Create a new user
New-ADUser -Name "John Doe" -GivenName "John" -Surname "Doe" -SamAccountName "jdoe" -UserPrincipalName "jdoe@lab.local" -Path "CN=Users,DC=lab,DC=local" -AccountPassword (ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force) -Enabled $true
