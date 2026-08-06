# Investigation Notes – Identity Security

## Investigation Scenario

A security alert has been generated indicating suspicious authentication activity involving a user account.

The objective is to determine whether the activity represents:


- User: John Smith
- Time: 02:13 AM
- Location: Australia
- Failed Sign-ins: 12
- Successful Sign-in: No
- Investigation Status: Initial Review

- Legitimate user behaviour
- Account compromise
- Credential abuse
- False positive detection

---

# Alert Summary

## User

John Smith

## Suspicious Activity

- Multiple failed sign-in attempts
- Successful authentication after failures
- Unusual login location
- Login occurring outside normal working hours


---

# Initial Assessment

The activity could indicate:

- Password spray attack
- Brute force attempt
- Stolen credentials
- VPN/proxy usage
- Legitimate travel
- Incorrect detection

Additional evidence is required before confirming compromise.

---

# Investigation Approach

The investigation follows the security analysis framework:

## Who?

Questions:

- Who owns the account?
- Is the user expected to access this resource?
- Does the user have privileged permissions?
- Has the account recently changed?

Evidence:

- User account details
- Assigned roles
- Group memberships
- Privileges

---

## What?

Questions:

- What application was accessed?
- What resources were accessed?
- Were any changes performed?

Evidence:

- Application access logs
- Audit logs
- File activity
- Administrative actions

---

## When?

Questions:

- When did the activity begin?
- Was the activity within normal working hours?
- Did successful access occur after failed attempts?

Evidence:

- Sign-in timestamps
- Activity timeline
- Authentication history

---

## Where?

Questions:

- Where did authentication originate?
- Is the location expected?
- Has this IP address been observed previously?

Evidence:

- IP address
- Geographic location
- Network information

---

## How?

Questions:

- Was MFA completed?
- What authentication method was used?
- Was the device trusted?
- Were Conditional Access policies applied?

Evidence:

- Authentication method
- Device information
- Conditional Access results

---

## Why?

Questions:

- Why was this activity considered suspicious?
- Was an existing security control missing?
- Could the attacker have bypassed controls?

Evidence:

- Risk detections
- Security policies
- Previous activity patterns

---

# Evidence Collection Checklist

Collect:

- User identity information
- Sign-in logs
- Authentication methods
- Device information
- IP address information
- Location details
- Application activity
- Privilege changes
- Security alerts

---

# Possible Indicators of Compromise

Indicators include:

- Multiple failed authentication attempts
- Successful login after failures
- New geographic location
- Impossible travel activity
- Unknown device
- Unusual application access
- Suspicious privilege changes

---

# Investigation Outcome

## Current Status

No confirmed compromise.

This investigation represents a simulated identity security investigation used to understand the workflow followed by security analysts.

---

# Recommended Response Actions

If compromise was confirmed:

1. Block suspicious authentication activity
2. Reset user credentials
3. Revoke active sessions
4. Require MFA re-registration
5. Review mailbox activity
6. Review file access activity
7. Check for privilege escalation
8. Continue monitoring

---

# Lessons Learned


Identity investigations should begin by validating whether the activity is expected or suspicious. Evidence from sign-in logs, MFA status, device information, and user context helps determine whether an account has been compromised.

Identity investigations require understanding:

- User behaviour
- Authentication patterns
- Access history
- Security controls
- Attack techniques

A security analyst must combine technical evidence with business context before making a decision.

---

# Future Improvements

Next investigation improvements:

- Analyse real Entra ID sign-in logs
- Create identity detection rules
- Write KQL queries
- Connect identity telemetry to Microsoft Sentinel
- Perform full incident response exercises

