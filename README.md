# 🚀 DevSecOps Security Testing Pipeline

Designed and implemented a DevSecOps security pipeline for a university inventory management system (IMS), integrating automated security testing directly into the software development lifecycle.

The project combines Static Application Security Testing (SAST) using Snyk, Dynamic Application Security Testing (DAST) using OWASP ZAP, and CI/CD automation through GitHub Actions and GitLab CI/CD. The objective was to continuously identify, analyse, remediate, and validate security vulnerabilities before deployment while improving security visibility and auditability.

---

## 📖 Project Overview

The Inventory Management System (IMS) consists of:

- React frontend
- FastAPI backend
- SQLite database
- JWT-based authentication
- Role-Based Access Control (RBAC)

To strengthen the security posture of the platform, automated vulnerability assessments were integrated into the CI/CD pipeline using DevSecOps principles.

The assessment focused on:

- Vulnerable third-party dependencies
- Browser-side security misconfigurations
- Runtime security weaknesses
- Security automation and continuous testing
- Vulnerability remediation and validation

---

## 🔍 Static Application Security Testing (SAST)

### Tool Used

- Snyk

### Objectives

- Identify vulnerable dependencies
- Detect known CVEs
- Assess software supply-chain risks
- Generate remediation recommendations

### Findings

#### Frontend Dependency Vulnerability

- Vulnerable package: `react-router-dom`
- High severity vulnerability
- CVSS Score: 7.2
- CWE-79 (Cross-Site Scripting)
- OWASP Top 10: A06 – Vulnerable and Outdated Components

#### Backend Dependency Vulnerability

- Vulnerable package: `zipp`
- Medium severity vulnerability
- CWE-835 (Infinite Loop Condition)
- OWASP Top 10: A06 – Vulnerable and Outdated Components

### Remediation

- Upgraded vulnerable frontend dependencies
- Updated backend packages to secure versions
- Re-ran scans to validate fixes

---

## 🌐 Dynamic Application Security Testing (DAST)

### Tool Used

- OWASP ZAP

### Objectives

- Analyse runtime behaviour
- Inspect HTTP responses
- Identify missing browser-side protections
- Validate security controls

### Findings

#### Missing Content Security Policy (CSP)

Risk:

- Increased exposure to malicious script execution
- Reduced protection against browser-side attacks

Remediation:

- Added Content-Security-Policy headers
- Restricted trusted resource origins
- Improved browser-side protection

---

#### Missing X-Frame-Options Header

Risk:

- Increased clickjacking exposure
- Unauthorised embedding within external frames

Remediation:

- Added:

```http
X-Frame-Options: DENY
```

- Implemented:

```http
frame-ancestors 'none'
```

within CSP policy.

---

#### Missing Subresource Integrity (SRI)

Risk:

- Browser unable to verify externally loaded resources
- Increased supply-chain attack exposure

Remediation:

- Removed external Google Fonts dependency
- Replaced with local system fonts
- Tightened Content Security Policy configuration

---

## ⚙️ DevSecOps CI/CD Pipeline

### GitHub Actions

Implemented an automated security workflow that:

- Installs project dependencies
- Runs Snyk vulnerability scans
- Executes OWASP ZAP baseline scans
- Generates security reports
- Uploads pipeline artifacts

### GitLab CI/CD

Pipeline stages include:

1. Dependency installation
2. SAST execution
3. Runtime deployment
4. DAST execution
5. Artifact generation
6. Security gate enforcement

### Security Gates

High-severity vulnerabilities automatically fail the pipeline to prevent insecure deployments.

---

## 📊 Security Artifacts Generated

The pipeline automatically generates:

### Snyk Reports

- Frontend vulnerability reports
- Backend vulnerability reports

### OWASP ZAP Reports

- HTML reports
- JSON reports
- Markdown reports

### Runtime Logs

- Frontend runtime logs
- Backend runtime logs

These artifacts improve:

- Traceability
- Auditability
- Security visibility
- Remediation tracking

---

## 🛡️ Security Controls Implemented

### Secure HTTP Headers

- Content Security Policy (CSP)
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy

### Dependency Security

- Automated dependency scanning
- Continuous vulnerability monitoring
- Secure package upgrades

### CI/CD Security

- Automated SAST testing
- Automated DAST testing
- Security gates
- Artifact retention

---

## 📈 Risk Assessment

The project utilised:

- OWASP Risk Rating Methodology
- OWASP Top 10 Mapping
- CWE Classification
- Vulnerability Prioritisation

Each identified vulnerability was:

1. Analysed
2. Risk-rated
3. Mapped to OWASP categories
4. Remediated
5. Re-tested

---

## 🔑 Skills Demonstrated

- DevSecOps
- GitHub Actions
- GitLab CI/CD
- SAST
- DAST
- Snyk
- OWASP ZAP
- OWASP Top 10
- Vulnerability Management
- Security Automation
- CI/CD Security Gates
- Software Supply Chain Security
- Secure Software Development Lifecycle (SSDLC)
- Security Hardening
- Security Testing

---

## 🎯 Outcomes

- Implemented automated security testing within CI/CD
- Identified and remediated dependency vulnerabilities
- Improved browser-side security controls
- Automated vulnerability reporting and artifact generation
- Introduced security gates to block insecure deployments
- Strengthened overall software development security posture
- Applied DevSecOps principles within a realistic development environment

---

## 🧰 Technologies Used

| Category | Technologies |
|-----------|-------------|
| Frontend | React, Vite |
| Backend | FastAPI, Python |
| Database | SQLite |
| SAST | Snyk |
| DAST | OWASP ZAP |
| CI/CD | GitHub Actions, GitLab CI/CD |
| Security | OWASP Top 10, CWE, OWASP Risk Rating |

---

## 📚 Topics Covered

- DevSecOps
- Continuous Security Testing
- Secure Software Development Lifecycle
- Dependency Vulnerability Management
- Security Automation
- CI/CD Security
- Runtime Security Assessment
- Supply Chain Security
- Secure Configuration Management
- Security Monitoring and Reporting
