# Web Application Security – CTF Writeups

## Coursework Evidence

A sanitised summary of the academic context, individual contribution,
tools, techniques and skills demonstrated in this project is available here:

**[View Coursework Evidence](evidence/COURSEWORK_EVIDENCE.md)**

---
Hands-on web application security analysis completed within an authorised
academic laboratory as part of my MSc Cybersecurity and Machine Learning studies.

This repository documents the investigation of eight web application security
challenges, focusing not only on identifying vulnerabilities but also on
understanding their root causes, security impact, mitigation strategies and
potential defensive detection opportunities.

> **Note:** Challenge secrets, credentials, internal laboratory URLs and
> assessment-specific sensitive information have intentionally been excluded.

---

## Security Areas Covered

| # | Security Topic | Key Concepts | OWASP Relevance |
|---|---|---|---|
| 01 | [Hardcoded Credentials](challenges/01-hardcoded-credentials/) | Client-side exposure, authentication security | Security Misconfiguration / Identification & Authentication |
| 02 | [HTTP Parameter Tampering](challenges/02-parameter-tampering/) | HTTP requests, access control, server-side validation | Broken Access Control |
| 03 | [OS Command Injection](challenges/03-command-injection/) | Input validation, command execution, server security | Injection |
| 04 | [Information Disclosure](challenges/04-information-disclosure/) | Static resources, information exposure, reconnaissance | Security Misconfiguration |
| 05 | [Cookie Authentication Bypass](challenges/05-cookie-authentication-bypass/) | Cookies, sessions, authentication | Identification & Authentication / Broken Access Control |
| 06 | [SQL Injection](challenges/06-sql-injection/) | Database security, injection, prepared statements | Injection |
| 07 | [LSB Steganography](challenges/07-lsb-steganography/) | Hidden data, file analysis, digital investigation | Not directly mapped |
| 08 | [JWT Security](challenges/08-jwt-security/) | JWT validation, token integrity, authorization | Identification & Authentication / Broken Access Control |

### OWASP Context

The OWASP mappings above indicate the security categories most relevant to
each exercise rather than claiming that every challenge represents an exact
one-to-one OWASP Top 10 classification.

Some exercises, such as LSB steganography, demonstrate broader cybersecurity
and investigation techniques rather than a specific OWASP web application
vulnerability.

## Tools & Technologies

- Firefox Developer Tools
- HTTP request analysis
- Browser storage and cookie analysis
- JSON Web Tokens (JWT)
- SQL and database security concepts
- Linux / operating-system security concepts
- Steganography analysis
- Web application security testing

---

## Skills Demonstrated

This project demonstrates practical experience in:

- Web application vulnerability analysis
- Authentication and authorization testing
- HTTP request and parameter analysis
- Input-validation testing
- SQL injection analysis
- OS command injection analysis
- Cookie and session-security analysis
- JWT security analysis
- Information-disclosure investigation
- Steganography and hidden-data analysis
- Vulnerability impact assessment
- Secure coding recommendations
- Defensive security analysis

---

## From Offensive Testing to Defensive Detection

My primary career interest is Security Analytics and AI-Driven Cybersecurity.

For this reason, selected challenge write-ups also consider how the observed
attack behaviour could potentially be detected using application, authentication,
web-server, endpoint or database telemetry.

A simplified defensive workflow is:

```text
Attack Activity
      ↓
Application / System Logs
      ↓
SIEM
      ↓
Detection Logic
      ↓
Security Alert
      ↓
Investigation
      ↓
Incident Response
