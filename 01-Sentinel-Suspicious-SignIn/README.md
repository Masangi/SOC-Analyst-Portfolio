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

This project uses fictional and sanitized data created for cybersecurity training and portfolio demonstration purposes. No employer, customer, or production data is included.
