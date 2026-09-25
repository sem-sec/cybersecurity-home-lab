# Windows Server & Active Directory Lab

## Environment
- Windows Server 2025 Standard (Desktop Experience), evaluation edition
- Deployed as a VirtualBox VM (DC01): 4GB RAM, 2 CPU cores, 40GB disk

## Setup Process
- Installed Windows Server 2025 from official Microsoft evaluation ISO
- Installed the Active Directory Domain Services (AD DS) role via Server Manager
- Promoted the server to a Domain Controller, creating a new forest and domain (corp.local)

## Objects Created
- Organizational Unit: Finance
- User account: sarah.mitchell (inside the Finance OU)
- Security group: Finance-Team (Global scope, Security type)
- Added sarah.mitchell as a member of Finance-Team

## Concepts Demonstrated
- OU-based organization of accounts for scalable management
- Group-based permission assignment vs. per-user permission assignment
- Practical application of centralized identity management principles used in enterprise environments

## Troubleshooting
- Resolved a black-screen boot issue after VM creation by switching the VirtualBox Graphics Controller setting (between VMSVGA and VBoxSVGA) and increasing allocated video memory
- Used the VirtualBox "Insert Ctrl-Alt-Del" input command (Right Ctrl + Delete) to unlock the Windows login screen, since the host OS intercepts the standard key combination

## Concepts Learned
- Domains, Domain Controllers, and how centralized authentication works
- Organizational Units (OUs) and Group Policy (GPO) for centralized management
- Kerberos authentication flow (TGT issuance, ticket-based resource access)
- Group-based permission management vs per-user permissions
- Security relevance: lateral movement and privilege escalation following an initial compromise

## Domain Join & Authentication

- Built a second VM (Client01, Windows 11 Pro) and joined it to the corp.local domain
- Configured NAT Network in VirtualBox so DC01 and Client01 could communicate
- Resolved a domain-join failure ("AD DC could not be contacted") by diagnosing and fixing DNS configuration on the client, pointing it to the domain controller's IP
- Troubleshot a client-side network adapter issue (disabled adapter causing "general failure" on ping) using ipconfig /release and /renew
- Successfully authenticated as a domain user (sarah.mitchell) on Client01, confirming Kerberos-based authentication against the domain controller
- Practiced AD account administration: reset a user's password via Active Directory Users and Computers
- Confirmed first-time domain login: Windows created a new local profile for the domain user on Client01, consistent with real-world AD first-login behavior

## Group Policy

- Created a GPO (Finance-Security-Policy) linked to the Finance OU
- Configured screen saver / lock policy settings (timeout, password protection)
- Applied the policy to a client machine using gpupdate /force
- Verified policy application using gpresult /r, confirming Finance-Security-Policy appeared under Applied Group Policy Objects for the domain user
- Learned that gpresult is the standard diagnostic tool for verifying Group Policy application in real environments, rather than relying on visual confirmation alone
