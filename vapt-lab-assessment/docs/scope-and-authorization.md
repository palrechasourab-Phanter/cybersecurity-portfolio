# Scope and Authorization

## Assessment Name

Authorized Vulnerability Assessment and Penetration Testing Lab

## Purpose

The purpose of this assessment is to identify and document security weaknesses in an isolated, intentionally vulnerable lab environment. The activity is intended solely for cybersecurity learning, professional skill development, and portfolio creation.

## Authorization

The target environment is self-hosted or explicitly authorized for testing. No testing is performed against public infrastructure, employer systems, client systems, or any third-party systems.

## In-Scope Assets

| Asset | Description | Environment |
|---|---|---|
| Target VM | Metasploitable 2, DVWA, OWASP Juice Shop, or equivalent | Isolated local virtual lab |
| Testing VM | Kali Linux or equivalent security testing system | Isolated local virtual lab |

## Permitted Activities

- Host discovery
- Port scanning
- Service enumeration
- Vulnerability scanning
- Web-application testing within the lab
- Manual validation of selected findings
- Evidence collection
- Security reporting
- Remediation recommendation development

## Out-of-Scope Activities

- Denial-of-service testing
- Social engineering
- Testing against public IP addresses
- Testing against employer or client systems
- Testing systems without written or explicit authorization
- Destructive actions
- Persistence, lateral movement, or data exfiltration outside the authorized lab objective

## Rules of Engagement

- Testing will remain restricted to the isolated lab environment.
- Evidence will be sanitized before publication.
- No passwords, tokens, private keys, employer data, or client data will be uploaded.
- Findings will be documented responsibly with remediation advice.
- The lab may be reset after testing if required.
