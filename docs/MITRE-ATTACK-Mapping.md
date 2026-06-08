# MITRE ATT&CK Mapping

## Overview

The following MITRE ATT&CK techniques were identified during log analysis activities.

---

## T1110 – Brute Force

### Description

Adversaries attempt to gain access by guessing passwords.

### Evidence

```text
authentication failure
incorrect password attempts
```

### Log Source

auth.log

---

## T1110.001 – Password Guessing

### Description

Repeated password guessing attempts against user accounts.

### Evidence

```text
3 incorrect password attempts
```

### Log Source

auth.log

---

## T1078 – Valid Accounts

### Description

Use of legitimate accounts for access.

### Evidence

```text
session opened for user root
```

### Log Source

auth.log

---

## T1098 – Account Manipulation

### Description

Modification or use of privileged accounts.

### Evidence

```text
sudo session opened
sudo session closed
```

### Log Source

auth.log

---

## T1033 – System Owner/User Discovery

### Description

Monitoring user activity and account usage.

### Evidence

```text
session opened
authentication events
```

### Log Source

auth.log

---

## MITRE ATT&CK Summary

| Technique ID | Technique |
|--------------|-----------|
| T1110 | Brute Force |
| T1110.001 | Password Guessing |
| T1078 | Valid Accounts |
| T1098 | Account Manipulation |
| T1033 | System Owner/User Discovery |
