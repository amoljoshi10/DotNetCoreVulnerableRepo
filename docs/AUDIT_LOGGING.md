# Audit Logging Configuration

## Purpose
This document describes the audit logging strategy for this application,
ensuring tamper-proof trails of security-relevant events.

## Events Logged
| Event Category | Examples | Retention |
|----------------|---------|-----------|
| Authentication | Login, logout, MFA, password reset | 1 year |
| Authorization  | Access denied, privilege change | 1 year |
| Data Access    | Read/write of sensitive records | 90 days |
| Configuration  | Admin changes, policy updates | 2 years |
| Security Scans | CI/CD scan results, findings | 90 days |

## Log Format (Structured JSON)
```json
{
  "timestamp": "2024-01-01T00:00:00Z",
  "event_type": "authentication.login",
  "actor": "user@example.com",
  "source_ip": "1.2.3.4",
  "resource": "/api/admin",
  "result": "success",
  "session_id": "abc123",
  "correlation_id": "req-xyz"
}
```

## Storage
- Logs written to append-only storage (S3 with Object Lock, Azure Immutable Blob)
- Log integrity verified with SHA-256 checksums
- Logs replicated to secondary region

## Access Control
- Log access restricted to security team and auditors
- Log deletion requires multi-party approval
- All log access is itself logged

## Alerting
- Failed login attempts: alert after 5 failures in 5 minutes
- Privilege escalation: immediate alert
- Mass data export: immediate alert
