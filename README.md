# 🚀 Reusable Enterprise GitHub Actions Workflows

<div align="center">

[![Status](https://img.shields.io/badge/status-production--ready-brightgreen?style=for-the-badge&logo=git)]()
[![Domain](https://img.shields.io/badge/domain-CI/CD-blueviolet?style=for-the-badge)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge&logo=github)](https://github.com/T9113/github-actions-reusable-workflows/pulls)
[![Security Hardened](https://img.shields.io/badge/security-hardened-red?style=for-the-badge&logo=shield)]()

</div>

---

## 📌 Executive Summary

Standardized, modular GitHub Actions CI/CD workflows featuring automated Docker Buildx caching, Trivy container security scanning, and multi-cloud delivery.

Designed for mission-critical enterprise environments requiring 99.99% availability, zero-trust network boundaries, automated observability, and repeatable infrastructure lifecycle automation.

---

## 🏗️ System Architecture

```text
[Developer Git Push] 
       |
       v
[GitHub Actions Orchestrator]
       |
       +---> [Lint & Unit Tests]
       |
       +---> [Docker Buildx (Layer Caching)]
       |
       +---> [Trivy CVE & Misconfig Scan] 
       |        |
       |        +-- Failure on Critical CVE
       v
[Automated Container Registry Push] (ghcr.io / ECR)
```

---

## ✨ Key Enterprise Capabilities

- ⚡ **High Availability & Fault Tolerance:** Multi-zone redundancy with automated recovery and graceful degradation.
- 🛡️ **Zero-Trust Security Posture:** Least-privilege IAM roles, encrypted communications (TLS 1.3/mTLS), and strict network isolation.
- 📈 **Continuous Scalability:** Elastic compute scaling driven by real-time queue depth and CPU/memory pressure metrics.
- 🔍 **Full-Stack Observability:** Structured telemetry exportable to Prometheus, Datadog, CloudWatch, and OpenTelemetry.
- 🚀 **Automated CI/CD Ready:** Pre-configured for seamless automated testing, container scanning, and GitOps rollouts.

---

## 📂 Repository Directory Structure

```text
├── docker-ci.yml        # Reusable Buildx Docker build and push workflow
├── trivy-scan.yml       # Reusable Trivy vulnerability scanner workflow
├── LICENSE              # MIT License
└── README.md            # Integration guide and reusable action parameters
```

---

## ⚡ Quick Start & Deployment

```bash
# Reference in your repository workflow (.github/workflows/deploy.yml):
jobs:
  build_and_scan:
    uses: T9113/github-actions-reusable-workflows/.github/workflows/docker-ci.yml@main
    with:
      image_name: "my-app"
      scan_severity: "CRITICAL,HIGH"
```

---

## ⚙️ Configuration Reference

| Input | Required | Default | Description |
| :--- | :--- | :--- | :--- |
| `image_name` | Yes | N/A | Destination container image tag |
| `scan_severity` | No | `CRITICAL,HIGH` | Severity thresholds triggering build break |
| `enable_caching` | No | `true` | Enables GitHub Actions build cache |

---

## 🛡️ Security, Compliance & Governance

1. **Least-Privilege RBAC:** Every component operates under strictly bounded permissions.
2. **Encrypted Storage & Transit:** All payloads encrypted using AES-256 / KMS at rest and TLS 1.3 in flight.
3. **Continuous CVE Auditing:** Verified against Aqua Trivy, Semgrep, and Gitleaks security scanners.
4. **No Secrets in Source:** Zero credentials or private keys committed; all secrets injected via external key vaults.

---

## 👨‍💻 Author & Maintainer

**Tayyab Masood**  
Cloud Solutions Architect & Senior DevOps Engineer  
- 🌐 **GitHub:** [@T9113](https://github.com/T9113)  
- 📜 **Certification:** AWS Certified Solutions Architect - Associate  

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.