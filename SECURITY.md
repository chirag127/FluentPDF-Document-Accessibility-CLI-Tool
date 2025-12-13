# Security Policy

## Reporting a Vulnerability

We take the security of `ReadablePDF-AI-Documents-To-Speech-CLI-Tool` seriously. If you believe you have discovered a security vulnerability, **do not open a public GitHub issue**.

Please report the issue to us privately by sending an email to: `chirag127.security@protonmail.com`.

Include the following information:
- A clear description of the vulnerability and its potential impact.
- Steps to reproduce the issue.
- Any relevant logs, screenshots, or proof-of-concept code.
- Your preferred method of contact and PGP key (if available).

We will acknowledge your report within **48 hours** and provide a timeline for resolution.

## Response Process

1. **Triage:** All reports are reviewed by the core security team.
2. **Verification:** We will attempt to reproduce and confirm the vulnerability.
3. **Prioritization:** Issues are ranked by severity (Critical, High, Medium, Low) based on CVSSv3 guidelines.
4. **Remediation:** A fix is developed and tested in a private branch.
5. **Disclosure:** Once patched, we will issue a public security advisory via GitHub and credit the reporter (unless anonymity is requested).

## Supported Versions

Only the latest stable release (`v1.0.0+`) receives security updates. Older versions are considered **unsupported** and may contain unpatched vulnerabilities.

## Security Best Practices

This tool processes sensitive document data. Follow these guidelines:

- **Never** process confidential or personally identifiable information (PII) without prior consent and encryption.
- Always run the tool in a sandboxed or isolated environment.
- Keep dependencies updated using `uv sync --locked`.
- Use the `--verify-ssl` flag when fetching remote documents.

## Third-Party Dependencies

We audit critical dependencies (e.g., TTS engines, PDF parsers) via automated SCA (Software Composition Analysis) in CI. Alerts are monitored via GitHub Dependabot.

Review our dependency tree:
bash
uv pip list --outdated


## Secure Configuration

Example of a secure `.env` configuration:
env
CEREBRAS_API_KEY=your_secure_key_here
TTS_ENGINE=coqui-ai
PDF_PARSER_MODE=safe-extract
LOG_LEVEL=WARNING
TEMP_DIR=/tmp/readablepdf-sandbox


## Security Audits

This repository undergoes quarterly automated scans using:
- Bandit (Python)
- Semgrep
- Trivy (filesystem & dependencies)

Scan results are logged internally and reviewed by the Apex Technical Authority.

For full audit logs, contact the maintainer.

---

*This document aligns with the Apex Technical Authority's Security Hardening Standard v9.2 (Dec 2025).*
*Repository: [https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool)*