# Windows Server & Active Directory Lab

## Environment
- Windows Server 2025 Standard (Desktop Experience), evaluation edition
- Deployed as a VirtualBox VM (DC01): 4GB RAM, 2 CPU cores, 40GB disk

## Setup Process
- Installed Windows Server 2025 from official Microsoft evaluation ISO
- Installed the Active Directory Domain Services (AD DS) role via Server Manager
- Promoted the server to a Domain Controller, creating a new forest and domain (corp.local)

## Troubleshooting
- Resolved a black-screen boot issue after VM creation by switching the VirtualBox Graphics Controller setting (between VMSVGA and VBoxSVGA) and increasing allocated video memory
- Used the VirtualBox "Insert Ctrl-Alt-Del" input command (Right Ctrl + Delete) to unlock the Windows login screen, since the host OS intercepts the standard key combination

## Concepts Learned
- Domains, Domain Controllers, and how centralized authentication works
- Organizational Units (OUs) and Group Policy (GPO) for centralized management
- Kerberos authentication flow (TGT issuance, ticket-based resource access)
- Group-based permission management vs per-user permissions
- Security relevance: lateral movement and privilege escalation following an initial compromise
