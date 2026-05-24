# Standard Operating Procedures (SOPs) & Runbooks

> **Standardized troubleshooting paths that reduce tribal knowledge and provide repeatable, evidence-driven incident resolution.**

[![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=Markdown&logoColor=FFFFFF)](https://daringfireball.net/projects/markdown/)&nbsp;[![Linux](https://img.shields.io/badge/Linux-222222?style=for-the-badge&logo=Linux&logoColor=FCC624)](https://kernel.org)

---

## The Impact

Authored and maintained **15+ comprehensive technical SOPs** covering compute, networking, identity, and application fault domains in cloud environments.

## The Value

Standardized common support tasks, **reduced tribal knowledge**, and improved the efficiency of the broader support team by providing repeatable troubleshooting paths. Each runbook follows a consistent `Symptoms → Triage → Investigation → Root Cause → Resolution → Validation → Prevention` structure, ensuring that any engineer on the team can execute them regardless of prior exposure to the specific failure mode.

---

## Runbook Structure

Every runbook follows a standardized diagnostic template ([`TEMPLATE.md`](runbooks/TEMPLATE.md)):

```text
Symptoms        → What does the failure look like?
Initial Triage  → Rapid, low-impact checks to isolate the fault domain
Investigation   → Step-by-step diagnostics with specific CLI commands
Root Cause      → The underlying technical failure mechanism
Resolution      → Clear steps to restore service integrity
Validation      → How to confirm the fix is effective
Prevention      → Proposed changes to eliminate the failure mode
```

---

## Runbook Index

### Compute

| Runbook | Scenario |
| ------- | -------- |
| [Disk Space Exhaustion](runbooks/compute/disk-full.md) | Root partition full — logrotate misconfiguration and uncapped journald |
| [High CPU Process](runbooks/compute/high-cpu-process.md) | Runaway process consuming CPU and degrading host performance |
| [Service Not Running](runbooks/compute/service-not-running.md) | Critical service down — systemd unit failure and dependency chain |

### Application

| Runbook | Scenario |
| ------- | -------- |
| [API Timeout (Upstream Delay)](runbooks/application/api-timeout.md) | HTTP 504s caused by third-party provider degradation |
| [Environment Misconfiguration](runbooks/application/env-misconfig.md) | Application failure due to missing or incorrect environment variables |
| [ELB Health Check Failure](runbooks/application/elb-health-fail.md) | Load balancer marking healthy targets as unhealthy |
| [K8s OOMKilled Pods](runbooks/application/k8s-oomkill.md) | Container memory limits exceeded causing pod evictions |
| [RDS Failover](runbooks/application/rds-failover.md) | Database failover event and application reconnection |
| [RDS Slow Queries](runbooks/application/rds-slow-queries.md) | Query performance degradation impacting application response times |
| [S3 Policy Block](runbooks/application/s3-policy-block.md) | Access denied errors due to bucket policy or ACL conflicts |
| [VPC Peering](runbooks/application/vpc-peering.md) | Cross-VPC connectivity failures and route table issues |
| [IAM Permission Boundaries](runbooks/application/iam-boundaries.md) | Effective permissions reduced by permission boundary policies |

### Identity & Access

| Runbook | Scenario |
| ------- | -------- |
| [IAM Access Denied](runbooks/identity/iam-access-denied.md) | Permission errors — policy evaluation, SCP boundaries, and trust relationships |

### Networking

| Runbook | Scenario |
| ------- | -------- |
| [DNS Resolution Failure](runbooks/networking/dns-resolution-failure.md) | Service unreachable due to DNS misconfiguration or propagation delay |
| [Security Group Block](runbooks/networking/security-group-block.md) | Traffic blocked by overly restrictive security group or NACL rules |

---

## Triage Flowchart

```text
[Start] → (External Check: Status 200?)
           |── No  → [Network / WAF Issue]
           |── Yes → (Local Check: Success?)
                      |── No  → [Application / Process Issue]
                      |── Yes → (Resource Check: Free space / CPU?)
                                |── No  → [Compute / Disk Issue]
                                |── Yes → [Upstream / Database Issue]
```

---

## Related Repositories

| Repository | Description |
| ---------- | ----------- |
| [**ops-diagnostics**](https://github.com/h-vance/ops-diagnostics) | Python & Bash diagnostic scripts for automated health verification, log analysis, and system profiling |
| [**log-rotation-maintenance**](https://github.com/h-vance/log-rotation-maintenance) | Automated Bash scripts for log rotation, compression, and storage cleanup on Linux servers |

---

Maintained by a Technical Support Engineer focused on operational reliability and incident response.