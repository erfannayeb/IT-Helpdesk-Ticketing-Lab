# INC-005 — User Cannot Complete MFA Setup — Authenticator App Not Working

**Type:** Incident  
**Priority:** High  
**Reported by:** p.wagner@corp.local  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 20 minutes  

---

## Problem
User reported being unable to log into Microsoft 365 after the company enforced Multi-Factor Authentication (MFA) for all accounts. When prompted to set up MFA, the Microsoft Authenticator app on their phone was not receiving push notifications and the QR code scan failed repeatedly. User was completely locked out of their M365 account including Outlook and Teams.

## Investigation
- User confirmed they had installed Microsoft Authenticator on their iPhone
- Asked user to check notification permissions for the Authenticator app — notifications were disabled in iPhone settings
- Even after enabling notifications, the QR code scan continued to fail
- Logged into **Microsoft 365 Admin Center → Users → Active users → selected the user**
- Navigated to **Manage multifactor authentication**
- Found the user had a corrupted MFA registration from a previous failed setup attempt

## Resolution
- In the M365 Admin Center, clicked **Manage multifactor authentication** for the user
- Selected the user and clicked **Delete** to clear all existing MFA methods
- Enabled notification permissions for Microsoft Authenticator in iPhone settings:
  - Settings → Microsoft Authenticator → Notifications → Allow
- Guided user through fresh MFA setup:
  - Signed into M365 → prompted for MFA setup
  - Selected **Microsoft Authenticator app**
  - Scanned QR code successfully on second attempt
  - Approved test push notification — confirmed working
- User logged in successfully with MFA on first attempt after setup

## Root Cause
The user had attempted MFA setup previously on a different device, leaving a corrupted incomplete registration in Azure AD. This blocked any new MFA setup attempts. Additionally, notification permissions for the Authenticator app were disabled on the iPhone, preventing push notifications from arriving.

## Prevention
Added a step to the company MFA rollout guide: before assisting users with MFA setup, always check and clear any existing MFA registrations in the admin center first. Also added iPhone notification permissions check to the standard MFA troubleshooting checklist.
