# Ticket Documentation

This folder contains detailed documentation for all tickets handled in the corp.local IT Helpdesk lab. Each ticket follows a standard structure used in real IT support environments: problem description, investigation steps, resolution, root cause analysis, and prevention recommendations.

---

## Ticket Index

| File | ID | Type | Title | Priority |
|------|----|------|-------|----------|
| [INC-001-account-locked.md](INC-001-account-locked.md) | INC-001 | Incident | User cannot log into Windows — account locked | High |
| [INC-003-outlook-crash.md](INC-003-outlook-crash.md) | INC-003 | Incident | Outlook crashes immediately on startup | Medium |
| [INC-004-vpn-failure.md](INC-004-vpn-failure.md) | INC-004 | Incident | VPN connection fails after password change | High |
| [SR-001-new-user-account.md](SR-001-new-user-account.md) | SR-001 | Service Request | New user account setup for new employee | Medium |
| [SR-002-adobe-install.md](SR-002-adobe-install.md) | SR-002 | Service Request | Install Adobe Acrobat Pro on laptop | Low |
| [SR-003-folder-access.md](SR-003-folder-access.md) | SR-003 | Service Request | Request access to shared network folder | Medium |
| [SUP-002-printer-not-found.md](SUP-002-printer-not-found.md) | SUP-002 | Support | Office printer on Floor 2 not showing on computer | Medium |

---

## Ticket Structure

Each ticket file follows this standard format:

```
- Ticket ID, Type, Priority, Reporter, Assignee, Status, Time to Resolve
- Problem description
- Investigation steps and tools used
- Resolution steps
- Root cause analysis
- Prevention recommendations
```

---

## Tools Used Across Tickets

| Tool | Used In |
|------|---------|
| Active Directory Users and Computers | INC-001, SR-001, SR-003, SUP-002 |
| Windows Event Viewer | INC-001 |
| Outlook Safe Mode | INC-003 |
| Windows Credential Manager | INC-004 |
| Remote Desktop (RDP) | INC-003, SR-002, SUP-002 |
| Group Policy (GPO / gpupdate) | SR-003, SUP-002 |
| Microsoft 365 Admin | SR-001 |
| Software Licence Portal | SR-002 |
