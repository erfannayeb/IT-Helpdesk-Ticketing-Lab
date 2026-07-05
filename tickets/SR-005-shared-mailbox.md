# SR-005 — Create Shared Mailbox for Finance Department

**Type:** Service Request  
**Priority:** Medium  
**Requested by:** f.mueller@corp.local (Finance Manager)  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 15 minutes  

---

## Request
Finance Manager requested a shared mailbox for the Finance department to handle incoming invoices and payment queries from external vendors. All Finance team members should be able to read and send emails from this mailbox.

## Actions Taken
- Logged into **Microsoft 365 Admin Center**
- Navigated to **Teams & groups → Shared mailboxes → Add a shared mailbox**
- Created shared mailbox:
  - Name: Finance Team
  - Email address: finance@corp.local
- Granted the following permissions to all Finance department members:
  - **Full Access** — allows reading and managing emails in the mailbox
  - **Send As** — allows sending emails as finance@corp.local
- Waited approximately 5 minutes for permissions to propagate
- Instructed Finance team members to add the shared mailbox in Outlook:
  - File → Account Settings → Add account → finance@corp.local
- Confirmed with Finance Manager that all team members could access and send from the shared mailbox

## Result
Shared mailbox finance@corp.local created and accessible by all 4 Finance team members. Team confirmed they can read incoming emails and send replies as the Finance team address.

## Root Cause
N/A — standard service request for a new shared resource.

## Notes
Shared mailboxes do not require a separate licence in Microsoft 365 as long as the mailbox size stays under 50GB. This was confirmed before creation.
