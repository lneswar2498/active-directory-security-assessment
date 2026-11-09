# Network and User Discovery in an Active Directory Lab

## Objective

This companion exercise documents the creation of a small Active Directory environment and the use of network and directory enumeration tools to understand exposed services and discoverable domain information.

## Environment

- Windows Server with Active Directory Domain Services (AD DS)
- Kali Linux assessment workstation
- Oracle VirtualBox lab network
- A test domain user created through Active Directory Users and Computers

## Workflow

1. Install and configure AD DS to provide centralized domain authentication.
2. Create a test domain user and configure its account.
3. Run Nmap discovery and service/version detection against the lab host.
4. Review SMB exposure with smbclient and enumerate SMB information with enum4linux.
5. Use nslookup to query DNS information.
6. Run additional Nmap checks and review Windows PowerShell output as recorded in the project report.

## Tools

| Tool | Purpose |
|---|---|
| Nmap | Host, port, and service discovery |
| smbclient | Interact with SMB shares in the authorized lab |
| enum4linux | Collect SMB and Windows-domain enumeration information |
| nslookup | Query DNS records |
| PowerShell | Review Windows-side system and domain information |
| Active Directory Users and Computers | Create and inspect test user objects |

## Assessment flow

```text
Windows Server + AD DS
        |
        +---- Create test domain user
        |
        v
Kali Linux
        |
        +---- Nmap service discovery
        +---- SMB share review
        +---- enum4linux enumeration
        +---- DNS lookup
        |
        v
Collected observations
        |
        v
Review exposure and recommend access controls
```

## Defensive takeaways

- Limit SMB exposure to trusted network segments.
- Review share permissions and avoid unnecessary anonymous access.
- Restrict LDAP and other domain services to systems that require them.
- Use strong identity controls and least-privilege permissions.
- Monitor authentication and directory-service activity.

## Evidence and limitations

The supplied report documents the setup and tools but does not provide a complete sanitized command transcript or a formal finding/severity table. Add redacted command output and screenshots from the lab to make the exercise independently reproducible. Do not publish passwords, hashes, or sensitive domain information.

## Responsible use

Perform enumeration only against lab systems or infrastructure for which you have explicit authorization.
