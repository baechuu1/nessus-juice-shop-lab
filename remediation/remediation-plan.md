# Remediation Plan

## High Priority
- Replace untrusted SSL/TLS certificates with certificates issued by a trusted Certificate Authority (CA)
- Ensure proper certificate chain configuration and validity

## Medium Priority
- Implement HTTPS for all application traffic and redirect HTTP requests to HTTPS
- Review application configuration to minimize unnecessary exposure of services

## Low Priority
- Review CORS policy and restrict allowed origins instead of using wildcard (*)
- Continue monitoring and scanning for newly introduced vulnerabilities

## Notes
OWASP Juice Shop is intentionally vulnerable and used in a controlled lab environment. Findings are analyzed from a real-world security perspective, even if some risks are expected in this setup.
