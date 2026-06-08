# Incident Analysis Report

## Incident Summary

During log analysis activities, multiple authentication-related security events were identified.

The investigation focused on authentication failures, privileged account activity, and session monitoring.

---

## Investigation Steps

1. Reviewed authentication logs
2. Filtered sudo events
3. Investigated root account access
4. Identified failed login attempts
5. Correlated authentication events
6. Analyzed session activity

---

## Timeline of Events

| Event Type | Observation |
|------------|-------------|
| Authentication Failure | Multiple failed login attempts detected |
| Incorrect Password Attempts | Three failed password attempts identified |
| Sudo Activity | Administrative commands executed |
| Root Access | Root sessions successfully established |
| Session Creation | User and system sessions recorded |

---

## Findings

### Authentication Failures

Evidence suggests repeated unsuccessful authentication attempts.

### Administrative Access

Root and sudo activity was successfully audited.

### Session Tracking

User sessions were correlated with authentication activity.

---

## Security Assessment

Risk Level: Medium

Reason:

Authentication failures combined with privileged access events require continuous monitoring to detect unauthorized access attempts.

---

## Conclusion

No malicious activity was confirmed. The events observed were consistent with authorized lab testing activities.
