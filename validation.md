\# Validation Notes



\## Manual Validation Steps



\- Verified OWASP Juice Shop was accessible at http://localhost:3000

\- Confirmed the Docker container was running using `docker ps`

\- Reviewed Nessus scan output for detected services and vulnerabilities



\## SSL/TLS Validation

\- Observed that the application does not use a trusted SSL certificate

\- Confirmed that HTTPS trust validation fails due to self-signed or untrusted certificate in a local lab environment



\## HTTP Service Validation

\- Used browser developer tools to inspect HTTP response headers

\- Confirmed the application responds over HTTP (no SSL/TLS encryption)



\## Additional Observations

\- Verified that supported cipher suites use strong encryption (AES-GCM, TLS 1.2/1.3)

\- Confirmed that encryption strength is strong, but trust is not established due to certificate issues



\## Notes

Validation was performed on select findings to confirm scan accuracy and demonstrate analysis of real-world vulnerability data.

