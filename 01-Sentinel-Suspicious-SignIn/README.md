# Microsoft Sentinel – Suspicious Sign-In Investigation

## Project Overview

This project demonstrates a SOC investigation of suspicious authentication activity using Microsoft Sentinel and Microsoft Entra ID logs.

The objective is to determine whether unusual sign-in activity represents an account compromise or legitimate user activity.

## Scenario

Microsoft Sentinel generates an alert after multiple failed authentication attempts are followed by a successful sign-in from an unusual location.

The SOC analyst must investigate the activity, determine the scope, identify indicators of compromise, and recommend appropriate response actions.

## Investigation Workflow

Alert Triage
↓
Review User & Source IP
↓
Analyze Sign-in History
↓
Check MFA & Conditional Access
↓
Identify Device and Location
↓
Search for Related Activity
↓
Determine Scope
↓
Containment Decision
↓
Document Findings

## Technologies

- Microsoft Sentinel
- Microsoft Entra ID
- KQL
- Conditional Access
- Microsoft Defender XDR
- MITRE ATT&CK

## Skills Demonstrated

- Alert triage
- Identity investigation
- KQL querying
- IOC analysis
- Incident scoping
- MITRE ATT&CK mapping
- Incident response
- SOC documentation

## Disclaimer

## Project Files

- [Investigation Queries](investigation-queries.kql) – KQL queries used to investigate authentication activity, suspicious IPs, Conditional Access, and affected users.
- [Incident Findings](incident-findings.md) – Investigation timeline, findings, MITRE ATT&CK mapping, containment recommendations, and analyst verdict.

## Key Investigation Result

The investigation identified repeated authentication failures followed by a successful sign-in from an unusual source.

Rather than immediately classifying the account as compromised, additional context was evaluated including:

- Authentication history
- Source IP activity
- MFA requirements
- Conditional Access results
- Other identities targeted by the source
- Post-authentication activity

**Final Classification:** Suspicious – Potential Account Compromise  
**Action:** Escalation and additional containment/validation recommended.

## SOC Skills Demonstrated

`Microsoft Sentinel` `KQL` `Entra ID` `Conditional Access` `Incident Response` `MITRE ATT&CK` `Identity Investigation` `Incident Scoping`
