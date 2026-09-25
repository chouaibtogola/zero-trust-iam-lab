# Enterprise Zero-Trust IAM Lab

This is my  hands-on lab simulating identity and access security for a fictional 500–1,000 employee company, built on Microsoft Entra ID with Conditional Access as the Zero-Trust policy engine.

> Microsoft describes Conditional Access as the policy engine at the heart of a Zero-Trust architecture — using signals like user, device, location, and risk to make real-time access decisions. This lab builds and tests that engine end-to-end.

## Why this project

I am pretty much delved within the realm of protecting systems from malicious actors , and the research of any vector that can hinder the overall digital security of a system. Humans(employees,users) are the main frontier of a company's vulnerability, thus Why I lately decided to pretty much focus all my expertise in researching within that security area. 

One core aspect of Identity and Access Management is the Zero-Trust. Most breaches occur due to giving more than enough privileges to accounts , which the latter if by any unfortunate mean are compromised, get leveraged by attackers to have access to confidential data and compromise the entire integrity of a system. 



## Architecture

![Architecture diagram](diagrams/architecture.png)

*[Four signal types : identity, device, location, and sign-in risk feed into Conditional Access, which evaluates them in real time and returns one of three outcomes: allow, challenge (step-up MFA), or block.]*

## What's implemented

| Area | Status |
|---|---|
| CA001 – MFA enforcement (all users) | ✅ |
| CA002 – Legacy authentication blocking | ✅ |
| CA003 – Device compliance requirements | ✅ |
| CA004 – Phishing-resistant auth for privileged accounts | ⏳ |
| CA005 – Untrusted location blocking | ✅ |
| CA006/CA007 – Risk-based sign-in policies (Identity Protection) | ✅ |
| CA008 – Guest/external user restrictions | ✅ |
| Break-glass emergency access accounts | ✅ |
| Privileged Identity Management (PIM) | ⏳ |
| Access reviews / entitlement management | ⏳ planned next |

## Repo structure

```
/policies/     Exported JSON of every Conditional Access policy
/scripts/      PowerShell/Graph SDK automation (bulk user creation, etc.)
/scenarios/    Test scenario write-ups with screenshots — the actual proof
/diagrams/     Architecture and policy-flow diagrams
/screenshots/  Supporting screenshots referenced by /scenarios
```

## Test scenarios

Each scenario below follows the same format: expected result → actual result → evidence. Full write-ups are in [`/scenarios`](./scenarios).

| # | Scenario | Expected | Actual |
|---|---|---|---|
| 1 | Employee, no MFA registered, MFA policy enforced | Challenged | ✅ Challenged — see [scenario 1](./scenarios/01-mfa-enforcement.md) |
| 2 | Admin without phishing-resistant auth | Blocked | [pending] |
| 3 | Risky sign-in (anonymized IP / impossible travel) | Challenged/Blocked | [pending] |
| 4 | Guest accessing sensitive app | Restricted | [pending] |
| 5 | Legacy auth client (IMAP/Basic Auth) | Blocked | [pending] |
| 6 | Non-compliant device | Blocked/Limited | [pending] |
| 7 | Privileged role activation via PIM | Allowed w/ justification | [pending] |
| 8 | Break-glass account sign-in | Always allowed | [pending] |

## Tech stack

Microsoft Entra ID (P2) · Conditional Access · Identity Protection · Privileged Identity Management (PIM) · Microsoft Graph PowerShell SDK · Log Analytics

## What I'd do differently in production

pending .....

## Demo video

Pending ....

---

*This is a lab environment using a fictional company and synthetic user data — no real employees, customers, or production systems are represented.*
