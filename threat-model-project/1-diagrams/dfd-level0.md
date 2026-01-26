# Level 0 Data Flow Diagram

```mermaid
flowchart LR
    P[Patient] -->|Health Data, Credentials| SC[Solaris Care Connect 360]
    D[Doctor] -->|Medical Records, Prescriptions| SC
    SC -->|Notifications, Reports| P
    SC -->|Patient Data, Alerts| D
    SC <-->|Claims, Verification| INS[Insurance Provider]
    SC <-->|Prescriptions| PHARM[Pharmacy Network]
    LAB[Lab Systems] -->|Test Results| SC
```

## External Entities
- **Patients**: End users accessing health data
- **Doctors**: Healthcare providers
- **Insurance**: Claims processing
- **Pharmacies**: Prescription fulfillment
- **Labs**: Test result delivery
