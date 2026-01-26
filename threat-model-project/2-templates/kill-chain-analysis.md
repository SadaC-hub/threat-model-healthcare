# Kill Chain Analysis - Solaris Care Connect 360

## Scenario 1: Ransomware Attack

```mermaid
flowchart TD
    style R fill:#ffcccc
    style W fill:#ffddcc
    style De fill:#ffeedd
    style Ex fill:#ffffcc
    style I fill:#ddffdd
    style C fill:#ccffff
    style A fill:#ccccff

    R[1. Reconnaissance<br/>LinkedIn, job postings] --> W[2. Weaponization<br/>Malicious PDF + macro]
    W --> De[3. Delivery<br/>Phishing email to HR]
    De --> Ex[4. Exploitation<br/>Macro execution]
    Ex --> I[5. Installation<br/>Backdoor + persistence]
    I --> C[6. Command & Control<br/>Reverse shell]
    C --> A[7. Actions<br/>Encrypt DB, ransom demand]
```

### Detection Opportunities

| Stage | Detection Method | Tool/Control |
|-------|-----------------|--------------|
| Reconnaissance | Monitor for data scraping | OSINT monitoring |
| Delivery | Email filtering | Email gateway, sandbox |
| Exploitation | Endpoint detection | EDR, application whitelisting |
| Installation | File integrity monitoring | HIDS, FIM |
| C2 | Network monitoring | NDR, DNS analysis |
| Actions | Database activity monitoring | DAM, DLP |

### Breaking the Chain

The earlier you detect, the better. Focus on:
- **Left of Boom**: Recon, Delivery (prevention)
- **Right of Boom**: Installation, C2, Actions (detection/response)

## Scenario 2: Insider Threat

```mermaid
flowchart TD
    R[1. Reconnaissance<br/>Employee knows systems] --> W[2. Weaponization<br/>Uses existing access]
    W --> De[3. Delivery<br/>N/A - already inside]
    De --> Ex[4. Exploitation<br/>Abuses privileges]
    Ex --> I[5. Installation<br/>Creates backup account]
    I --> C[6. Command & Control<br/>Uses legitimate tools]
    C --> A[7. Actions<br/>Exports patient data]
```

### Insider-Specific Controls
- User behavior analytics (UBA)
- Data Loss Prevention (DLP)
- Privileged Access Management (PAM)
- Regular access reviews
