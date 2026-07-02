# INC-001 — User Cannot Log Into Windows

**Type:** Incident  
**Priority:** High  
**Reported by:** m.schmidt@corp.local  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 12 minutes  

---

## Problem
User reported being unable to log into their Windows workstation on Monday morning. The screen displayed the message: *"Your account has been locked. Please contact your administrator."*

## Investigation
- Opened **Active Directory Users and Computers**
- Located the user account — confirmed it was locked
- Checked **Event Viewer → Windows Logs → Security** on the affected workstation
- Found Event ID 4740 (account lockout) — lockout originated from workstation `PC-04`
- No signs of unauthorized access — lockout caused by repeated failed login attempts from the user themselves

## Resolution
- Unlocked the user account in Active Directory
- Reset the password and enabled "User must change password at next logon"
- Called the user and confirmed successful login
- Advised user on the company password policy (account locks after 5 failed attempts)

## Root Cause
User forgot their password after the company-wide password reset the previous Friday and triggered the lockout threshold.

## Prevention
Suggested enrolling the user in the self-service password reset (SSPR) portal to avoid future lockouts requiring IT intervention.
