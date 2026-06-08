# Risk Assessment Report

## Project

Linux Syslog Security Monitoring Lab

## Assessment Type

Security Log Analysis and Risk Evaluation

## Platform

Ubuntu Linux 24.04 LTS

---

# Executive Summary

A risk assessment was conducted using Linux authentication and system logs collected through rsyslog.

The objective was to evaluate authentication activity, privileged account usage, and potential indicators of unauthorized access.

The analysis identified several security-relevant events including authentication failures, privileged account access, and administrative actions.

No active threats or confirmed compromises were detected during the investigation.

---

# Risk Matrix

| Risk ID | Finding | Likelihood | Impact | Risk Level |
|----------|----------|------------|---------|------------|
| R-01 | Failed Authentication Attempts | Medium | Medium | Medium |
| R-02 | Root Account Activity | Medium | High | Medium |
| R-03 | Administrative Sudo Usage | Low | Medium | Low |
| R-04 | User Session Activity | Low | Low | Low |

---

# Risk R-01

## Failed Authentication Attempts

### Description

Authentication logs recorded multiple failed password attempts.

### Evidence

```text
authentication failure
3 incorrect password attempts
```

### Potential Threats

- Credential stuffing
- Password guessing
- Brute-force attacks

### MITRE ATT&CK

| Technique ID | Technique |
|-------------|------------|
| T1110 | Brute Force |
| T1110.001 | Password Guessing |

### Risk Rating

Medium

### Recommended Controls

- Strong password policy
- Multi-factor authentication
- Failed login alerting
- Account lockout policy

---

# Risk R-02

## Privileged Account Access

### Description

Root account access events were identified during the investigation.

### Evidence

```text
session opened for user root
```

### Potential Threats

- Privilege abuse
- Unauthorized administration
- Insider threats

### MITRE ATT&CK

| Technique ID | Technique |
|-------------|------------|
| T1078 | Valid Accounts |

### Risk Rating

Medium

### Recommended Controls

- Restrict root login
- Monitor privileged accounts
- Enable administrative auditing
- Review access regularly

---

# Risk R-03

## Administrative Command Execution

### Description

Sudo activity was successfully logged and monitored.

### Evidence

```text
sudo session opened
sudo session closed
```

### Potential Threats

- Unauthorized administrative changes
- Configuration misuse

### MITRE ATT&CK

| Technique ID | Technique |
|-------------|------------|
| T1098 | Account Manipulation |

### Risk Rating

Low

### Recommended Controls

- Monitor sudo activity
- Enable command auditing
- Review administrative logs

---

# Risk R-04

## User Session Activity

### Description

User session creation and termination events were recorded.

### Evidence

```text
session opened
session closed
```

### Potential Threats

- Unauthorized access
- Suspicious login behavior

### MITRE ATT&CK

| Technique ID | Technique |
|-------------|------------|
| T1033 | System Owner/User Discovery |

### Risk Rating

Low

### Recommended Controls

- Monitor user sessions
- Review authentication logs
- Investigate unusual login patterns

---

# Security Recommendations

## Authentication Security

- Implement MFA
- Enforce strong passwords
- Configure account lockout policies

---

## Privileged Access Management

- Restrict direct root login
- Monitor sudo activity
- Implement least privilege

---

## Continuous Monitoring

- Deploy centralized logging
- Configure alerting rules
- Review authentication events regularly

---

## Cloud Security Relevance

The skills demonstrated in this project directly align with security monitoring practices used in:

- Google Cloud Logging
- AWS CloudWatch Logs
- Microsoft Sentinel
- Splunk
- ELK Stack
- Wazuh
- SOC Operations

---

# Final Risk Assessment

Overall Risk Level: **Medium**

Reason:

The environment generated authentication failures and privileged account activity, demonstrating realistic security monitoring scenarios. While no compromise was identified, these events represent behaviors commonly investigated by SOC Analysts and Cloud Security Engineers.
