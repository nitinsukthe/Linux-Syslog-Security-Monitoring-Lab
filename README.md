# Linux Syslog Security Monitoring Lab

## SOC Analyst Project | Linux Log Analysis | Security Monitoring | MITRE ATT&CK Mapping

![Linux](https://img.shields.io/badge/Linux-Ubuntu-orange)
![Syslog](https://img.shields.io/badge/Logging-rsyslog-blue)
![SOC](https://img.shields.io/badge/SOC-Log%20Analysis-success)
![MITRE](https://img.shields.io/badge/MITRE-ATT%26CK-red)

---

# Project Overview

This project demonstrates practical Security Operations Center (SOC) analyst skills through the investigation and analysis of Linux system logs using Ubuntu and the rsyslog logging framework.

Using syslog and authentication logs, system events, user activity, failed authentication attempts, sudo usage, privileged account access, and session events were analyzed to identify security-relevant activity and develop incident investigation capabilities.

The project simulates real-world Blue Team and SOC monitoring activities including:

* Log Analysis
* Security Monitoring
* Authentication Auditing
* Threat Detection
* Incident Investigation
* Event Correlation
* Risk Assessment
* MITRE ATT&CK Mapping

---

# Project Objectives

* Understand Linux logging architecture
* Verify rsyslog configuration and operation
* Investigate Linux syslog events
* Analyze authentication logs
* Detect failed login attempts
* Monitor privileged account activity
* Investigate sudo usage
* Correlate security events
* Perform MITRE ATT&CK mapping
* Produce professional security documentation

---

# Skills Demonstrated

## Security Operations

* Log Analysis
* Security Monitoring
* Authentication Auditing
* Threat Detection
* Event Investigation
* Event Correlation
* Risk Assessment
* Security Reporting

## Linux Security

* Ubuntu Administration
* Syslog Analysis
* Authentication Log Analysis
* Sudo Monitoring
* Root Access Auditing
* Linux Log Management

## SOC Analyst Competencies

* Incident Investigation
* Security Event Monitoring
* Threat Hunting Fundamentals
* MITRE ATT&CK Mapping
* Security Documentation
* Blue Team Methodology

---

# Lab Environment

| Component        | Details                     |
| ---------------- | --------------------------- |
| Operating System | Ubuntu 24.04 LTS            |
| Logging Service  | rsyslog                     |
| Log Sources      | syslog, auth.log            |
| Log Location     | /var/log                    |
| Analysis Tools   | grep, awk, less, sort, uniq |
| Analyst Role     | SOC Analyst                 |

---

# Project Architecture

```text
Linux System
      │
      ▼
   rsyslog
      │
      ▼
  /var/log/
      │
 ┌────┼───────────────┐
 ▼    ▼               ▼
syslog auth.log    kern.log
      │
      ▼
 Log Analysis
      │
      ▼
 Security Findings
      │
      ▼
 MITRE ATT&CK Mapping
      │
      ▼
 Incident Report
```

---

# Project Walkthrough

## Step 1 – Verify System Information

Verified hostname, current user, and Ubuntu version.

### Screenshot

```text
screenshots/01-Ubuntu-System-Info.png
```

![System Information](screenshots/01-Ubuntu-System-Info.png)

---

## Step 2 – Verify rsyslog Service

Confirmed rsyslog was running and actively collecting logs.

### Screenshot

```text
screenshots/02-Rsyslog-Service-Status.png
```

![Rsyslog Status](screenshots/02-Rsyslog-Service-Status.png)

---

## Step 3 – Review Syslog Configuration

Reviewed logging modules and configuration inheritance.

### Screenshots

![Rsyslog Modules](screenshots/03-Rsyslog-Modules.png)

![Rsyslog Include Config](screenshots/04-Rsyslog-IncludeConfig.png)

---

## Step 4 – Review Linux Log Sources

Investigated available log files within `/var/log`.

### Screenshot

![Log Directory](screenshots/05-Var-Log-Directory.png)

---

## Step 5 – Analyze Syslog Events

Reviewed operating system and service events.

### Screenshot

![Syslog Entries](screenshots/06-Syslog-Entries.png)

---

## Step 6 – Investigate Systemd Events

Filtered and analyzed system service activity.

### Screenshot

![Systemd Events](screenshots/07-Systemd-Events.png)

---

## Step 7 – Review Scheduled Task Events

Analyzed CRON-related system activity.

### Screenshot

![CRON Events](screenshots/08-CRON-Events.png)

---

## Step 8 – Authentication Log Analysis

Reviewed user authentication activity.

### Screenshot

![Authentication Logs](screenshots/09-Authentication-Log-Review.png)

---

## Step 9 – Investigate Sudo Activity

Monitored privileged command execution.

### Screenshot

![Sudo Activity](screenshots/10-Sudo-Activity.png)

---

## Step 10 – Session Monitoring

Tracked successful user and administrative sessions.

### Screenshot

![Session Events](screenshots/11-Session-Opened-Events.png)

---

## Step 11 – Failed Login Detection

Identified authentication failures and unsuccessful login attempts.

### Screenshot

![Failed Login Detection](screenshots/12-Failed-Login-Detection.png)

---

## Step 12 – Failed Login Metrics

Calculated failed authentication activity.

### Screenshot

![Failed Login Count](screenshots/13-Failed-Login-Count.png)

---

## Step 13 – Log Source Analysis

Identified the most frequent system log sources.

### Screenshot

![Log Source Analysis](screenshots/14-Most-Frequent-Log-Sources.png)

---

## Step 14 – Password Failure Investigation

### Screenshot

![Incorrect Password Attempts](screenshots/15-Incorrect-Password-Attempts.png)

---

## Step 15 – Root Access Monitoring

### Screenshot

![Root Access Events](screenshots/16-Root-Access-Events.png)

---

# Key Findings

| Finding                        | Result   |
| ------------------------------ | -------- |
| rsyslog Running                | Yes      |
| Authentication Logs Available  | Yes      |
| Syslog Monitoring Operational  | Yes      |
| Failed Authentication Attempts | 3        |
| Root Account Activity          | Detected |
| Sudo Activity                  | Detected |
| User Session Events            | Detected |
| Security Findings Generated    | Yes      |

---

# MITRE ATT&CK Mapping

| Tactic                        | Technique                   | ID        |
| ----------------------------- | --------------------------- | --------- |
| Credential Access             | Brute Force                 | T1110     |
| Credential Access             | Password Guessing           | T1110.001 |
| Defense Evasion / Persistence | Valid Accounts              | T1078     |
| Persistence                   | Account Manipulation        | T1098     |
| Discovery                     | System Owner/User Discovery | T1033     |

## Observed Activity

```text
authentication failure
incorrect password attempts
session opened for user root
sudo session opened
session opened
```

These events resemble behaviors frequently investigated by SOC analysts during authentication monitoring and account security investigations.

---

# Security Recommendations

### Authentication Security

* Enforce strong password policies
* Implement Multi-Factor Authentication (MFA)
* Configure account lockout policies

### Privileged Access Management

* Restrict direct root logins
* Monitor sudo activity
* Apply least privilege principles

### Continuous Monitoring

* Deploy centralized logging
* Configure authentication failure alerts
* Monitor privileged account activity

### Recommended Platforms

* Splunk
* ELK Stack
* Wazuh
* Microsoft Sentinel
* Google Cloud Logging
* AWS CloudWatch Logs

---

# Documentation

### Reports

* reports/Linux-Syslog-Analysis-Report.pdf

### Findings

* findings/Security-Findings.md
* findings/Risk-Assessment.md

### Analysis Documents

* docs/Project-Overview.md
* docs/Syslog-Configuration-Analysis.md
* docs/Authentication-Log-Analysis.md
* docs/Incident-Analysis.md
* docs/MITRE-ATTACK-Mapping.md
* docs/Remediation-Recommendations.md

### Commands

* commands/Syslog-Analysis-Commands.txt

---

# Learning Outcomes

Through this project, I gained practical experience in:

* Linux Log Analysis
* Authentication Monitoring
* Failed Login Detection
* Root Access Auditing
* Security Event Investigation
* Threat Detection Fundamentals
* Incident Investigation Methodology
* MITRE ATT&CK Mapping
* Security Documentation
* SOC Analyst Workflows

---

# Author

**Nitin Sukthe**

Future SOC Analyst | Future Cloud Security Engineer

Focused on Security Operations, Cloud Security, Threat Detection, Log Analysis, Incident Investigation, and Blue Team Engineering.
