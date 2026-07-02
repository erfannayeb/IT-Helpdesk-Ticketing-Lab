# INC-004 — VPN Connection Fails After Password Change

**Type:** Incident  
**Priority:** High  
**Reported by:** k.braun@corp.local  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 15 minutes  

---

## Problem
User working from home reported being unable to connect to the company VPN after completing a mandatory password change the previous evening. VPN client showed error: *"Authentication failed. Please check your credentials."*

## Investigation
- Called the user to troubleshoot remotely (could not use RDP as VPN was not connected)
- Asked user to open the VPN client and attempt connection — confirmed authentication error
- Suspected cached credentials issue — VPN client was still using the old password stored in Windows Credential Manager
- Instructed user to open **Control Panel → Credential Manager → Windows Credentials**
- Found entry for the company VPN with the old credentials stored

## Resolution
- Instructed user to delete the old VPN credential entry from Credential Manager
- User re-entered VPN credentials with the new password
- VPN connected successfully on the first attempt
- Confirmed user had full access to internal resources

## Root Cause
Windows Credential Manager had cached the user's previous VPN password. After the mandatory password change, the VPN client was attempting to authenticate with the old cached credentials instead of prompting for new ones.

## Prevention
Added a note to the company password change procedure advising users working remotely to clear cached VPN credentials after every password change.
