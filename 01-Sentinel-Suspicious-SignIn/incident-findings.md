# Incident Findings – Suspicious Sign-In Investigation

## Incident Summary

Microsoft Sentinel generated an alert for suspicious authentication activity involving the fictional user:

**User:** alex.johnson@contoso.com

Multiple failed authentication attempts were observed from an unfamiliar external IP address, followed by a successful authentication.

The objective of the investigation was to determine whether the account had been compromised and identify the potential scope of the activity.

---

## Initial Alert Details

| Field | Value |
|---|---|
| Alert Type | Suspicious Sign-In Activity |
| Severity | Medium |
| User | alex.johnson@contoso.com |
| Source IP | 203.0.113.50 |
| Data Source | Microsoft Entra ID Sign-in Logs |
| Investigation Platform | Microsoft Sentinel |
| Status | Investigated |

> All users, IP addresses, timestamps, and findings in this project are fictional and created for portfolio demonstration purposes.

---

## Investigation Timeline

### 09:12 UTC – Failed Authentication Activity

Multiple failed authentication attempts were observed against:

alex.johnson@contoso.com

Source:

203.0.113.50

The number and frequency of failures warranted additional investigation.

### 09:18 UTC – Successful Authentication

A successful authentication was subsequently observed from the same source IP.

This increased the priority of the investigation because repeated failures followed by a success can indicate password guessing, credential stuffing, or legitimate user error.

### 09:21 UTC – Sign-In Context Reviewed

The analyst reviewed:

- Source IP
- Geographic information
- Application accessed
- Authentication requirement
- Conditional Access result
- Sign-in history

The source did not match the fictional user's expected sign-in pattern.

### 09:27 UTC – Scope Investigation

Additional KQL queries were used to determine whether the source IP had attempted authentication against other accounts.

This step was performed to identify the potential blast radius and determine whether the activity represented an isolated account event or broader credential-based activity.

### 09:35 UTC – Incident Escalation

Based on the combination of authentication failures, subsequent success, unusual source characteristics, and deviation from the user's expected activity, the event was treated as suspicious and escalated for containment.

---

## Investigation Findings

The investigation identified:

- Multiple authentication failures from the same external source.
- A subsequent successful authentication.
- Sign-in activity inconsistent with the fictional user's normal pattern.
- Activity requiring further validation of MFA and Conditional Access results.
- The need to investigate whether additional identities were targeted by the same source.

No conclusion was based solely on geographic location or IP reputation. Multiple authentication and contextual indicators were considered together.

---

## MITRE ATT&CK Mapping

### T1110 – Brute Force

The repeated authentication attempts may be consistent with password guessing or credential-based attacks.

### T1078 – Valid Accounts

If stolen credentials were successfully used, the attacker may have obtained access through a valid account.

---

## Recommended Containment Actions

If the activity were confirmed as malicious, recommended actions would include:

1. Disable or temporarily restrict the affected account.
2. Revoke active sessions and authentication tokens.
3. Force a password reset.
4. Verify or re-register MFA where appropriate.
5. Block confirmed malicious indicators when supported by organizational policy.
6. Search for additional users targeted by the same infrastructure.
7. Review post-authentication activity for suspicious access or changes.
8. Continue monitoring for recurrence.

---

## Analyst Verdict

**Classification:** Suspicious – Potential Account Compromise

**Escalation:** Required

The evidence justifies escalation and additional containment; however, the authentication pattern alone is not sufficient to conclusively prove account compromise.

Additional validation should include user confirmation, MFA details, device information, Conditional Access results, and post-authentication activity.

---

## Lessons Learned

This investigation demonstrates that a SOC analyst should not classify an account as compromised based on a single indicator.

Effective identity investigation requires correlation of:

Authentication activity → Source → Device → MFA → Conditional Access → User behavior → Related accounts → Post-login activity

This approach helps reduce false positives while ensuring potentially compromised identities receive appropriate investigation and response.
