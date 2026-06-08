# Authentication Log Analysis

## Objective

Analyze Linux authentication logs to identify user activity, login events, privileged account usage, and authentication failures.

---

## Log Source

```bash
/var/log/auth.log
```

---

## Authentication Events Investigated

### User Session Activity

Command:

```bash
grep "session opened" /var/log/auth.log
```

Observed Events:

- User login sessions
- Root account sessions
- PAM authentication activity

---

### Sudo Activity

Command:

```bash
grep "sudo" /var/log/auth.log
```

Observed Events:

- Sudo command execution
- Session opening and closing
- Administrative account usage

---

### Authentication Failures

Command:

```bash
grep "authentication failure" /var/log/auth.log
```

Observed Events:

- Failed password attempts
- Authentication rejection events

---

## Findings

### Successful Logins

Multiple successful session creation events were recorded for authorized users.

### Administrative Access

Multiple sudo and root session events were identified.

### Failed Authentication Attempts

Three authentication failure events were detected during testing.

---

## Security Value

Authentication logs provide visibility into:

- User activity
- Administrative access
- Failed login attempts
- Potential brute-force attacks
- Privilege escalation events

---

## Conclusion

Authentication log analysis successfully identified both successful and failed authentication activity and provided valuable insight into system access patterns.
