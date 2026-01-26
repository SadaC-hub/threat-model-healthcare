# STRIDE Threat Register - Solaris Care Connect 360

## Spoofing Threats

| ID | Threat | Component | Description | Severity |
|----|--------|-----------|-------------|----------|
| S1 | Credential Theft | Auth Service | Attacker obtains patient credentials via phishing | High |
| S2 | Fake Doctor Accounts | Admin Portal | Attacker creates unauthorized doctor accounts | Critical |
| S3 | Token Forgery | API Gateway | API requests made with stolen/forged JWT tokens | High |
| S4 | MITM on Insurance | External API | Man-in-the-middle attack on insurance provider API | Medium |
| S5 | Lab Result Spoofing | Lab Integration | Fake lab results injected into system | Critical |

## Tampering Threats

| ID | Threat | Component | Description | Severity |
|----|--------|-----------|-------------|----------|
| T1 | Record Modification | Patient Records | Unauthorized changes to patient medical records | Critical |
| T2 | Prescription Alteration | Rx Service | Changing drug dosages or medications | Critical |
| T3 | Audit Log Tampering | Audit Service | Deleting or modifying audit trails | High |
| T4 | Claims Manipulation | Insurance API | Modifying insurance claim amounts | High |
| T5 | Vitals Data Tampering | Monitoring | Altering real-time vital signs data | Critical |


## Repudiation Threats

| ID | Threat | Component | Description | Severity |
|----|--------|-----------|-------------|----------|
| R1 | Prescription Denial | Rx Service | Doctor denies approving prescription | High |
| R2 | Access Denial | Patient Records | Patient denies accessing their records | Medium |
| R3 | Permission Change Denial | Admin Portal | Admin denies changing user permissions | High |
| R4 | Claim Receipt Denial | Insurance API | Insurance provider denies receiving claim | Medium |
| R5 | Export Audit Gap | Data Export | No audit trail for bulk data exports | High |

## Information Disclosure Threats

| ID | Threat | Component | Description | Severity |
|----|--------|-----------|-------------|----------|
| I1 | SQL Injection | Patient Records | Patient records exposed via SQLi | Critical |
| I2 | Excessive Data Return | API Gateway | API returns more data than needed | High |
| I3 | Verbose Errors | All Services | Error messages reveal system internals | Medium |
| I4 | Unencrypted Transit | Network | Data transmitted without TLS | Critical |
| I5 | Exposed Backups | Storage | Backup files accessible without auth | Critical |
| I6 | Log Leakage | All Services | PHI accidentally logged | High |

## Denial of Service Threats

| ID | Threat | Component | Description | Severity |
|----|--------|-----------|-------------|----------|
| D1 | DDoS Attack | API Gateway | Distributed denial of service | High |
| D2 | DB Exhaustion | Database | Expensive queries exhaust DB | High |
| D3 | Storage Exhaustion | File Storage | Unlimited uploads fill storage | Medium |
| D4 | Account Lockout | Auth Service | Mass account lockout attack | Medium |
| D5 | Resource Exhaustion | Rx Service | Processing overload | High |

## Elevation of Privilege Threats

| ID | Threat | Component | Description | Severity |
|----|--------|-----------|-------------|----------|
| E1 | Patient to Doctor | Auth Service | Patient gains doctor privileges | Critical |
| E2 | Doctor to Admin | Auth Service | Doctor gains admin access | Critical |
| E3 | SQLi to DBA | Database | SQL injection leads to DBA access | Critical |
| E4 | Container Escape | Infrastructure | Container breakout to host | Critical |
| E5 | IDOR | Patient Records | Access other patients' records | High |
