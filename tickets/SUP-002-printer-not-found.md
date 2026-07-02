# SUP-002 — Printer Not Showing Up on Computer

**Type:** Support  
**Priority:** Medium  
**Reported by:** g.richter@corp.local  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 18 minutes  

---

## Problem
User reported that the office printer on Floor 2 was no longer visible on their computer after returning from two weeks of annual leave. Other users on the same floor could print without issues.

## Investigation
- Remoted into the user's workstation via RDP
- Opened **Settings → Bluetooth & devices → Printers & scanners** — printer `HP-LaserJet-Floor2` was not listed
- Checked other workstations on the same floor — printer was present on all of them
- Checked **Group Policy** — printer deployment is handled via GPO for the `Floor2_Users` group
- Found that the user's account had been moved to a different OU during an AD cleanup while they were on leave, removing them from the `Floor2_Users` group

## Resolution
- Moved the user account back to the correct OU in Active Directory
- Added user back to the `Floor2_Users` security group
- Ran `gpupdate /force` on the user's workstation
- Printer `HP-LaserJet-Floor2` appeared automatically within 2 minutes
- User confirmed successful test print

## Root Cause
An Active Directory cleanup performed during the user's absence incorrectly moved the user account to a different OU, removing them from the GPO-based printer deployment group.

## Prevention
Flagged the AD cleanup process to the senior sysadmin — recommended adding a verification step to check group memberships before moving accounts between OUs.
