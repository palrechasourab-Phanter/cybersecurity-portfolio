# Authorized Vulnerability Assessment and Penetration Testing Lab

## Project Overview

This project documents an authorized vulnerability assessment and penetration-testing exercise performed against an intentionally vulnerable virtual-machine environment.

The purpose of this assessment is to demonstrate a structured security-testing workflow, including reconnaissance, service enumeration, vulnerability scanning, manual validation, risk prioritization, remediation planning, and professional reporting.

## Authorization Statement

All activities in this project are performed only in an isolated, self-hosted, intentionally vulnerable lab environment.

No public IP addresses, employer systems, client systems, third-party infrastructure, or unauthorized applications were scanned, accessed, modified, or disrupted.

## Target Environment

| Item | Details |
|---|---|
| Target | Metasploitable 2 / DVWA / OWASP Juice Shop |
| Environment | Isolated virtual lab |
| Hypervisor | VirtualBox or VMware Workstation |
| Assessment Type | Vulnerability Assessment and Penetration Testing |
| Assessment Status | In Progress |
| Assessment Date | To be added after completion |

## Objectives

- Identify live hosts and exposed services in the authorized lab environment
- Perform service and version enumeration
- Identify vulnerabilities using vulnerability-scanning tools
- Validate selected findings manually in a safe and authorized manner
- Prioritize findings using CVSS-based severity principles
- Provide practical remediation recommendations
- Produce a professional assessment report

## Methodology

The assessment follows these phases:

1. Scope confirmation and lab authorization
2. Host discovery and network reconnaissance
3. Port scanning and service enumeration
4. Vulnerability scanning
5. Manual validation of selected findings
6. Risk analysis and severity prioritization
7. Remediation recommendation development
8. Final assessment reporting

## Tools Used

| Tool | Purpose |
|---|---|
| Nmap | Host discovery, port scanning, service detection, and enumeration |
| Nessus or OpenVAS | Vulnerability scanning and risk identification |
| Burp Suite | Web-application security testing and request analysis |
| Nikto | Web-server security and misconfiguration checks, if applicable |
| Searchsploit | Public exploit research, if applicable |
| Bash | Evidence collection and limited local automation |

## Repository Contents

```text
vapt-lab-assessment/
├── README.md
├── docs/
│   ├── scope-and-authorization.md
│   ├── methodology.md
│   └── remediation-checklist.md
├── evidence/
│   └── README.md
├── report/
│   └── README.md
└── scripts/
    └── README.md
```

## Planned Deliverables

- Scope and authorization document
- Assessment methodology document
- Sanitized evidence and tool output
- Findings summary with severity ratings
- Detailed vulnerability findings
- Remediation checklist
- Professional Vulnerability Assessment and Penetration Testing report in Markdown and PDF format

## Key Skills Demonstrated

- Network reconnaissance
- Service enumeration
- Vulnerability assessment
- Web-application testing fundamentals
- CVSS-based risk prioritization
- OWASP Top 10 awareness
- Security-report writing
- Remediation planning
- Ethical and authorized security testing

## Disclaimer

This repository is created for educational and professional portfolio purposes. It contains only authorized lab work and sanitized evidence. The content must not be used to test, scan, exploit, or access systems without explicit permission.
