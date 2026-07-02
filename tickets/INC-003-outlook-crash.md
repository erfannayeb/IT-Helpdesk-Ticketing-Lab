# INC-003 — Outlook Not Opening — Crashes on Startup

**Type:** Incident  
**Priority:** Medium  
**Reported by:** t.hoffmann@corp.local  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 25 minutes  

---

## Problem
User reported that Microsoft Outlook crashes immediately on startup. The application splash screen appears briefly then closes with no error message. User had no access to email for approximately 2 hours before raising the ticket.

## Investigation
- Remoted into the workstation via RDP
- Attempted to launch Outlook — confirmed the crash behaviour
- Checked **Event Viewer → Application Logs** — found repeated error referencing a third-party add-in: `CRM_Connector.dll`
- Launched Outlook in Safe Mode using `outlook.exe /safe` — application opened successfully, confirming an add-in was causing the crash
- Opened **File → Options → Add-ins → COM Add-ins** — identified `CRM Connector` add-in as the faulty component

## Resolution
- Disabled the `CRM Connector` add-in
- Restarted Outlook normally — opened successfully
- Notified the user and confirmed email access was restored
- Raised a separate ticket with the software team to investigate the faulty CRM add-in and provide an updated version

## Root Cause
A recent automatic update to the CRM Connector add-in introduced a compatibility issue with the current version of Microsoft Outlook (Microsoft 365, version 2405).

## Prevention
Recommended that software updates for third-party add-ins be tested in a staging environment before being pushed to all users.
