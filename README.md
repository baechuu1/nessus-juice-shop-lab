# Vulnerability Assessment Lab: Nessus Scan Against OWASP Juice Shop

## Overview
This project demonstrates a vulnerability assessment workflow using Nessus against OWASP Juice Shop deployed in a local Docker environment. The objective was to simulate real-world vulnerability scanning, analysis, validation, and remediation planning.

## Objectives
- Deploy a vulnerable web application in a controlled lab
- Perform a vulnerability scan using Nessus
- Analyze and prioritize findings
- Validate select findings manually
- Develop remediation recommendations

## Lab Environment
- Host System: Windows
- Scanner: Nessus
- Target: OWASP Juice Shop
- Deployment Method: Docker
- Target URL: http://localhost:3000

## Methodology
1. Deployed OWASP Juice Shop using Docker
2. Verified application accessibility
3. Configured and executed a Nessus scan
4. Reviewed findings based on severity and relevance
5. Validated select findings manually
6. Documented remediation recommendations

## Key Findings

### 1. SSL Certificate Cannot Be Trusted (Medium)
- Certificate trust validation failed due to improper or self-signed certificate
- Potential risk of man-in-the-middle attacks

### 2. HTTP Service Without Encryption (Informational)
- Application communicates over HTTP without SSL/TLS
- Risk of data interception

### 3. SSL/TLS Cipher Suites (Informational)
- Strong encryption (AES-GCM, TLS 1.2/1.3) is supported
- Demonstrates proper cryptographic configuration despite trust issues

nessus-juice-shop-lab/
├── README.md
├── screenshots/
├── reports/
├── notes/
└── remediation/


## Disclaimer
This project was conducted in an authorized local lab environment for educational purposes only.

## Observations
The scan produced primarily informational findings with one medium-severity issue. This reflects a realistic scenario where vulnerability scans generate large volumes of low-severity data that require analysis and prioritization.

## Project Structure
