<center>
<h1>Cloud Operations Runbook</h1>
<p><em>Standardized operational procedures for maintaining enterprise cloud environments.</em></p>
<img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform">&nbsp;<img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS">&nbsp;<img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions">
</center>

---

<h1>Cloud Operations Runbook</h1>


- `runbooks/compute/`: VM lifecycle management, Linux system resource optimization, Disk I/O, and CPU saturation.
- `runbooks/identity/`: IAM policy troubleshooting, permission scoping, and Service Account management.
- `runbooks/application/`: REST API failure analysis, environment configuration, and upstream dependency timeouts.

- **Symptoms**: Observed errors, failed metrics, or reported system behavior.
- **Initial Triage**: Rapid, low-impact checks to quickly isolate the primary fault domain.
- **Investigation**: Step-by-step diagnostic procedures with specific CLI commands and observability queries.
- **Root Cause Analysis**: Deep-dive into the underlying technical failure mechanism.
- **Resolution**: Clear, documented steps required to restore service integrity.
- **Validation**: Verification procedures to confirm the fix is effective and has no side effects.
- **Prevention**: Proposed architectural or procedural changes to eliminate the failure mode.