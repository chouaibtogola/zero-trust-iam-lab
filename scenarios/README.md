
## [Scenario 3] —  Admin blocked without phishing-resistant auth 

**Policy:** CA004 - Require phishing-resistant MFA for Tier0 admins 
**Date tested:** 9/19/2026
**Objective:** Demonstrates that privileged accounts must use FIDO2/Windows Hello/certificate-based auth, not SMS or regular push MFA

**Setup:**
- User: YounoussK / Security Engineer
- Starting state:  no phishing-resistant method registered

**Expected result:** Blocked/Challenged for admin, Not applied for regular employee
**Actual result:**   Conditional Access: CA004 enforced

**Evidence:**
<img width="1905" height="875" alt="image" src="https://github.com/user-attachments/assets/a726716f-3e9d-43db-bb66-9b8427b3bcca" />
 for the admin user

 
- ../screenshots/ca004-employee-not-applied.png  for any regular user other than admin group
- `CA004-policy.json` — exported policy definition

**Business takeaway (1–2 sentences for the README/LinkedIn):**

Even if an admin's password and regular MFA are phished, this policy prevents sign-in without a phishing-resistant method.
This closes a gap where privileged accounts, if compromised via phishing, could otherwise authenticate with a simple SMS code. Requiring phishing-resistant MFA for Tier0 admins removes that path entirely.
