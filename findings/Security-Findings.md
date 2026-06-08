# Security Findings

## Project

Linux Syslog Security Monitoring Lab

## Analyst

Nitin Sukthe

## Environment

- Ubuntu 24.04 LTS
- rsyslog
- Linux Syslog
- Authentication Logs (auth.log)

---

# Executive Summary

A security-focused analysis of Linux system logs was conducted using rsyslog, syslog, and authentication logs. The investigation focused on authentication events, privileged account activity, failed login attempts, and system-level event monitoring.

Multiple authentication failures, privileged account sessions, and administrative activities were successfully identified and analyzed using native Linux log analysis techniques.

No evidence of malicious compromise was observed. All detected events were generated during controlled lab testing.

---

# Finding 1: Failed Authentication Attempts

## Severity

Medium

## Description

Multiple failed authentication attempts were detected within the authentication logs.

Authentication failures are important indicators because they may represent:

- Password guessing attempts
- Brute-force activity
- Unauthorized access attempts
- Misconfigured user accounts

---

## Evidence

```text
authentication failure
3 incorrect password attempts
```

---

## Log Source

```text
/var/log/auth.log
```

---

## Security Impact

Repeated authentication failures may indicate attempts to gain unauthorized access to a Linux system.

If left unmonitored, attackers may eventually compromise weak credentials.

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|-------------|------------|
| T1110 | Brute Force |
| T1110.001 | Password Guessing |

---

# Finding 2: Root Account Access Activity

## Severity

Medium

## Description

Root account session activity was identified within authentication logs.

Monitoring privileged accounts is critical because root access provides unrestricted control over the operating system.

---

## Evidence

```text
session opened for user root
```

---

## Log Source

```text
/var/log/auth.log
```

---

## Security Impact

Unauthorized use of privileged accounts can lead to:

- System compromise
- Configuration modification
- Persistence establishment
- Log tampering

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|-------------|------------|
| T1078 | Valid Accounts |

---

# Finding 3: Sudo Activity Monitoring

## Severity

Informational

## Description

Administrative activity was successfully recorded through sudo authentication events.

The logs demonstrated that administrative commands executed by authorized users were fully auditable.

---

## Evidence

```text
sudo session opened
sudo session closed
```

---

## Log Source

```text
/var/log/auth.log
```

---

## Security Impact

Monitoring sudo activity enables:

- User accountability
- Administrative auditing
- Security investigations
- Incident response support

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|-------------|------------|
| T1098 | Account Manipulation |

---

# Finding 4: User Session Tracking

## Severity

Informational

## Description

User login sessions were successfully identified and correlated with authentication activity.

---

## Evidence

```text
session opened
session closed
```

---

## Security Impact

Session monitoring helps identify:

- User access patterns
- Unauthorized access
- Account misuse
- Privilege escalation activity

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|-------------|------------|
| T1033 | System Owner/User Discovery |

---

# Overall Security Assessment

The Linux system successfully generated authentication and system logs required for security monitoring.

The analysis demonstrated:

- Authentication monitoring
- Failed login detection
- Privileged account auditing
- Security event correlation
- Incident investigation techniques

No indicators of compromise were identified during the assessment.

---

# Key Security Capabilities Demonstrated

- Log Analysis
- Security Monitoring
- Authentication Auditing
- Linux Administration
- Incident Investigation
- Threat Detection
- Event Correlation
- MITRE ATT&CK Mapping
