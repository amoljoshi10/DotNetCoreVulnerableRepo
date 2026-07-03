# Incident Response Plan

## Scope
This plan covers all security incidents affecting this application,
its infrastructure, and associated data.

## Incident Severity Levels
| Level | Description | Response Time |
|-------|-------------|---------------|
| P1 — Critical | Data breach, ransomware, service down | Immediate (24/7) |
| P2 — High | Active exploitation, significant data exposure | 1 hour |
| P3 — Medium | Vulnerability exploited but contained | 4 hours |
| P4 — Low | Suspicious activity, no confirmed impact | 24 hours |

## Roles
| Role | Responsibility |
|------|----------------|
| Incident Commander | Coordinates overall response |
| Technical Lead | Leads investigation and containment |
| Communications Lead | Internal and external communications |
| Security Analyst | Evidence collection and forensics |

## Response Phases

### 1. Identification
- Detect incident via monitoring, alerting, or report
- Create incident ticket and assign severity
- Page Incident Commander

### 2. Containment
- Isolate affected systems if needed
- Preserve evidence (do NOT delete logs)
- Block attacker access

### 3. Eradication
- Remove malware or attacker persistence
- Patch exploited vulnerability
- Rotate compromised credentials

### 4. Recovery
- Restore services from known-good backups
- Verify integrity before going live
- Monitor for signs of re-compromise

### 5. Post-Incident Review
- Conduct blameless postmortem within 5 business days
- Document timeline, impact, and lessons learned
- Update this plan based on findings

## Contacts
- Security Team: security@your-org.com
- On-call: See PagerDuty / OpsGenie
- Legal (for data breach): legal@your-org.com
