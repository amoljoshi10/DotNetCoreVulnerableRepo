# Centralized Logging Dashboard

## Overview

All application and system logs are aggregated into a centralized platform for visualization and alerting.

## Log Sources

| Source | Log Type | Retention |
|--------|----------|-----------|
| Application servers | App logs, errors | 90 days |
| Web/API gateway | Access logs, latency | 30 days |
| Databases | Query logs, slow queries | 30 days |
| CI/CD pipelines | Build and deploy logs | 90 days |
| Security tools | SAST/DAST/SCA results | 1 year |
| Authentication | Login events, MFA | 1 year |

## Key Dashboards

- **Application Health:** Error rate, latency p50/p95/p99, throughput
- **Security Events:** Failed logins, suspicious IPs, secret scan findings
- **CI/CD Metrics:** Build times, failure rates, deployment frequency
- **Infrastructure:** CPU/memory/disk, container restarts

## Alerting Rules

| Alert | Condition | Severity |
|-------|-----------|----------|
| High error rate | Error rate > 5% for 5 min | High |
| Auth failures | > 10 failed logins in 1 min | Critical |
| Secret detected | Any secret in scan | Critical |
| Build failure | 3 consecutive failures | Medium |

## Access

- Dashboard URL: [Add your logging platform URL]
- Access: RBAC — read for developers, full access for ops/security
