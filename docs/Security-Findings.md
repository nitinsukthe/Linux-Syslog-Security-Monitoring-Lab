# Security Findings

## Finding 1: Authentication Failures Detected

### Severity

Medium

### Evidence

```text
authentication failure
3 incorrect password attempts
```

### Impact

Failed login attempts may indicate:

- Password guessing
- Brute-force attempts
- Unauthorized access attempts

### MITRE ATT&CK

T1110 – Brute Force

---

## Finding 2: Root Account Activity Observed

### Severity

Medium

### Evidence

```text
session opened for user root
```

### Impact

Root account activity should be monitored to prevent unauthorized administrative access.

### MITRE ATT&CK

T1078 – Valid Accounts

---

## Finding 3: Administrative Activity Detected

### Severity

Informational

### Evidence

```text
sudo session opened
sudo session closed
```

### Impact

Administrative actions were successfully logged and auditable.

### MITRE ATT&CK

T1098 – Account Manipulation

---

## Overall Assessment

No active compromise was identified.

However, authentication failures and privileged account activity demonstrate the importance of continuous log monitoring and security auditing.
