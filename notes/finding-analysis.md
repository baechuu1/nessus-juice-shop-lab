
# Finding Analysis

## Finding 1: SSL Certificate Cannot Be Trusted
- Severity: Medium
- Port/Service: TLS/SSL Service
- Description: The server’s X.509 certificate cannot be trusted due to issues in the certificate chain. This may include a self-signed certificate, missing intermediate certificates, expired validity, or an unverified signature.
- Why It Matters: An untrusted SSL/TLS certificate prevents proper verification of the server’s identity. This can allow attackers to perform man-in-the-middle (MITM) attacks, intercepting or modifying traffic between users and the application.
- Validation Notes: Reviewed Nessus plugin output indicating the certificate chain could not be verified. This behavior is expected in a local lab environment using self-signed certificates.
- Recommended Remediation: Replace the certificate with one issued by a trusted Certificate Authority (CA) or properly configure the certificate chain to include valid intermediate certificates. Ensure certificates are within valid date ranges and use supported signing algorithms.

## Finding 2: HTTP Service Exposed Without Encryption
- Severity: Informational
- Port/Service: TCP 3000 / HTTP
- Description: Nessus identified that the web application is accessible over HTTP without SSL/TLS encryption. The server responds using HTTP/1.1 and does not support HTTPS.
- Why It Matters: Without encryption, data transmitted between the client and server can be intercepted or modified by attackers. This increases the risk of eavesdropping and man-in-the-middle (MITM) attacks.
- Validation Notes: Confirmed by accessing http://localhost:3000 and observing that the application does not use HTTPS. Nessus output also indicates "SSL: no".
- Recommended Remediation: Configure the application to use HTTPS with a valid SSL/TLS certificate. Redirect all HTTP traffic to HTTPS to ensure secure communication.

## Finding 4: Supported SSL/TLS Cipher Suites
- Severity: Informational
- Port/Service: TLS/SSL Service
- Description: Nessus identified the supported SSL/TLS cipher suites for the server, including TLS 1.2 and TLS 1.3 configurations using strong encryption algorithms such as AES-GCM.
- Why It Matters: Cipher suites determine how securely data is encrypted during transmission. Weak or outdated ciphers can expose systems to cryptographic attacks. In this case, only strong cipher suites are supported, indicating secure encryption practices.
- Validation Notes: Reviewed Nessus output showing TLS 1.2 and TLS 1.3 support with AES-GCM encryption and ECDHE key exchange, which provides forward secrecy.
- Recommended Remediation: No immediate remediation required. Continue to enforce strong cipher suites and disable any deprecated or insecure protocols such as SSLv3 or weak ciphers if introduced in the future.
