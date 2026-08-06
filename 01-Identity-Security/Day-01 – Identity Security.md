# Investigation Notes – Day 1

## Investigation Scenario

An alert was generated for suspicious sign-in activity involving a user account.

### Alert Summary

- User: John Smith
- Time: 02:13 AM
- Location: Australia
- Failed Sign-ins: 12
- Successful Sign-in: No
- Investigation Status: Initial Review

---

# Initial Assessment

The alert could indicate:

- Password spray attack
- Credential compromise
- Legitimate user travelling
- VPN usage
- False positive

Further investigation is required before concluding the account has been compromised.

---

# Evidence to Collect

## Identity Information

- Username
- User department
- Assigned roles
- Privileged access
- MFA status

---

## Sign-in Details

Collect:

- Timestamp
- IP Address
- Country
- City
- Device Name
- Browser
- Operating System
- Sign-in Result
- Authentication Method

---

## Questions to Answer

### Who?

Who owns the account?

Who approved the login?

---

### What?

What applications were accessed?

What actions were performed after sign-in?

---

### When?

When did the first failed login occur?

When did the successful login occur?

Were there any sign-ins afterwards?

---

### Where?

Which country?

Which IP address?

Has this IP been seen before?

---

### How?

Was MFA used?

Was Conditional Access applied?

Was the device compliant?

---

### Why?

Why was the login considered suspicious?

Was the user expected to be in this location?

---

# Possible Indicators of Compromise

- Multiple failed logins
- Successful login after failures
- New geographic location
- Unusual sign-in time
- New device
- Impossible travel
- High-risk sign-in

---

# Possible Response Actions

If compromise is confirmed:

- Block sign-in
- Reset password
- Revoke active sessions
- Require MFA re-registration
- Review mailbox rules
- Review file access
- Notify the user
- Continue monitoring

---

# Lessons Learned

Identity investigations should begin by validating whether the activity is expected or suspicious. Evidence from sign-in logs, MFA status, device information, and user context helps determine whether an account has been compromised.
