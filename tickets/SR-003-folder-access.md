# SR-003 — Request Access to Shared Network Folder

**Type:** Service Request  
**Priority:** Medium  
**Requested by:** n.wolf@corp.local  
**Approved by:** f.mueller@corp.local (Department Manager)  
**Assigned to:** Erfan Nayeb  
**Status:** Resolved  
**Time to Resolve:** 10 minutes  

---

## Request
User requested read/write access to the shared network folder `\\fileserver01\Finance\Projects` for collaboration on the Q3 budget report.

## Actions Taken
- Verified manager approval was included in the ticket (company policy requires manager sign-off for shared folder access)
- Opened **Active Directory Users and Computers**
- Located the security group `Finance_Projects_RW` which controls access to the requested folder
- Added user `n.wolf` to the `Finance_Projects_RW` group
- Waited for group policy to propagate (approximately 5 minutes)
- Confirmed with user that they could access and write to the folder successfully

## Result
Access granted within 10 minutes of ticket assignment. User confirmed full read/write access to the Finance Projects folder.

## Note
Access was granted based on explicit manager approval. Reminder added to IT calendar to review this access in 90 days as per the company's access review policy.
