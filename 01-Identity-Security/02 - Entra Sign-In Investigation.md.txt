# 02 — Entra ID Sign-In Investigation

## Project Overview

This project demonstrates an evidence-based approach to investigating a potentially compromised Microsoft Entra ID user account.

The investigation focuses on identifying suspicious authentication activity, correlating it with post-authentication behaviour, assessing business impact, and defining appropriate containment and remediation actions.

**Project Type:** Simulated SOC / Incident Response Investigation
**Environment:** Microsoft Entra ID / Microsoft 365
**Status:** Investigation methodology completed; technical lab evidence to be added

---

## 1. Business Scenario

A Finance user's Microsoft Entra ID account generated a suspicious sign-in from an unusual geographic location using an unknown device.

Following the authentication, the account accessed Exchange Online, created an external mailbox forwarding rule, and accessed a large number of emails.

The objective was to determine whether the activity represented legitimate user behaviour or potential account compromise.

---

## 2. Security Problem

The organisation needs to detect and investigate potentially compromised user accounts before attackers can use them to access sensitive corporate resources or perform fraudulent activities.

The investigation focused on:

* Authentication activity
* User and device context
* Geographic anomalies
* MFA activity
* Conditional Access results
* Post-authentication behaviour
* Potential business impact

---

## 3. Risk

The affected user works in Finance, increasing the potential business impact.

Potential consequences include:

* Financial information exposure
* Business Email Compromise
* Invoice or payment fraud
* Exposure of supplier or customer information
* Sensitive internal communication exposure
* Data theft
* Further compromise of accounts or systems

---

## 4. User Context

| Attribute          | Observation              |
| ------------------ | ------------------------ |
| User               | Sarah Williams           |
| Department         | Finance                  |
| Normal location    | Sydney                   |
| Normal device      | Corporate Windows laptop |
| Privileged account | No                       |

---

## 5. Suspicious Sign-In

| Attribute          | Observation          |
| ------------------ | -------------------- |
| Time               | 09:42                |
| Location           | Singapore            |
| IP                 | `198.51.100.25`      |
| Application        | Microsoft Office 365 |
| Resource           | Exchange Online      |
| Device             | Unknown              |
| Operating System   | Windows 11           |
| Browser            | Chrome               |
| Result             | Successful           |
| MFA                | Successful           |
| Conditional Access | Passed               |

---

## 6. Post-Authentication Activity

| Time  | Activity                                 |
| ----- | ---------------------------------------- |
| 09:45 | Exchange Online accessed                 |
| 09:47 | External mailbox forwarding rule created |
| 09:50 | Large number of emails accessed          |

The post-authentication activity significantly increased the suspicion associated with the original sign-in.

---

## 7. Investigation Timeline

```text
09:42
Successful authentication from Singapore
        ↓
09:42
Unknown device observed
        ↓
09:45
Exchange Online accessed
        ↓
09:47
External forwarding rule created
        ↓
09:50
Large number of emails accessed
```

The sequence of events provides stronger evidence than the suspicious authentication alone.

---

## 8. Indicators of Compromise

Potential indicators identified during the investigation:

* Source IP: `198.51.100.25`
* Singapore geolocation
* Previously unknown device
* External mailbox forwarding destination
* Unusual Exchange Online activity
* Large-scale email access

An IOC is an indicator that warrants investigation. It does not automatically prove malicious activity.

---

## 9. Evidence

The following observations supported the investigation:

1. The user's normal working location was Sydney.
2. A successful authentication originated from an IP geolocated to Singapore.
3. The authentication originated from an unknown device.
4. Exchange Online was accessed shortly afterward.
5. An external mailbox forwarding rule was created.
6. A large number of emails were accessed.

---

## 10. Finding

### Primary Finding

**The account is likely compromised.**

This assessment is based on the combination of:

```text
Unusual location
+
Unknown device
+
Successful authentication
+
Exchange Online access
+
External forwarding rule
+
Large-scale email access
```

Successful MFA does not independently prove that the legitimate user performed the activity.

---

## 11. Immediate Containment

Recommended containment actions:

1. Revoke active sessions/tokens associated with the account.
2. Reset the user's credentials.
3. Require secure reauthentication and MFA.
4. Remove the suspicious external forwarding rule.
5. Investigate and restrict suspicious device access where appropriate.
6. Verify the activity with the legitimate user.

Containment should follow the organisation's incident-response procedures.

---

## 12. Further Investigation

### Identity

Investigate:

* Additional suspicious sign-ins
* Unusual locations
* Authentication anomalies
* MFA events
* Risk detections

### Network

Investigate:

* Other users authenticating from the same IP
* IP reputation
* Other activity associated with the source IP

### Device

Investigate:

* Device ownership
* Device registration
* Device compliance
* Other accounts using the device

### Email

Investigate:

* Forwarding destination
* Emails accessed
* Emails downloaded
* Emails sent
* Emails deleted
* Additional mailbox rules

### Enterprise Scope

Search for:

* Other users showing similar activity
* Same IP
* Same device indicators
* Same forwarding destination
* Similar authentication patterns

---

## 13. Remediation

The organisation should determine how the attacker was able to obtain or use the account.

Potential remediation areas include:

* Stronger authentication controls
* Risk-based Conditional Access
* Managed/compliant device requirements
* Improved protection for Finance users
* Monitoring of suspicious mailbox-rule creation
* Improved suspicious sign-in detection
* Stronger phishing-resistant authentication

---

## 14. Security Improvement

### Before

Suspicious authentication could potentially be followed by abnormal mailbox activity without sufficient correlation or detection.

### Improvement

Implement correlated detection for:

```text
Unusual Sign-In
      +
Unknown Device
      +
Exchange Online Access
      +
New External Forwarding Rule
```

This provides stronger detection than relying on a single suspicious authentication event.

---

## 15. Lessons Learned

### Identity

MFA reduces authentication risk but does not eliminate the possibility of account compromise.

### Investigation

Authentication events should be investigated alongside subsequent user activity.

### Evidence

Multiple correlated events provide stronger evidence than a single indicator.

### Business Impact

The user's business role should be considered when assessing the severity of an identity incident.

### Detection

Mailbox forwarding-rule creation can be an important post-authentication indicator and should be monitored.

---

## 16. Future Technical Work

The technical components of this project will be added as we complete them.

Planned work includes:

* Entra ID sign-in log analysis
* KQL fundamentals
* Suspicious sign-in queries
* Conditional Access investigation
* Mailbox activity investigation
* Detection engineering
* Threat-hunting exercises
* Incident-response playbooks

No simulated evidence in this project is presented as real-world corporate telemetry.

---

## 17. Conclusion

This investigation demonstrates an evidence-based approach to identifying potential Entra ID account compromise.

The investigation moved from:

**Suspicious authentication → Evidence collection → Timeline construction → Account compromise assessment → Containment → Remediation**

The key investigative principle is:

> **Do not investigate authentication in isolation. Correlate identity, device, location, authentication and post-authentication activity to determine what actually happened.**
