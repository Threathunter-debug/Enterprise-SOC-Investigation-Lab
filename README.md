## Investigation Objective

Investigate repeated authentication failures detected within QRadar SIEM to determine whether activity was associated with brute-force attacks, compromised credentials, or legitimate service account validation behavior.

## Environment

- Enterprise Windows Environment
- Active Directory Authentication
- QRadar SIEM
- CrowdStrike Falcon
- Tanium
- Infoblox Grid Manager
- Microsoft Windows Security Logs

- 
## Tools Used

| Tool | Purpose |
|------|----------|
| IBM QRadar | SIEM correlation and offense analysis |
| CrowdStrike Falcon | Endpoint threat validation |
| Tanium | Endpoint visibility and process investigation |
| Infoblox | IP attribution and network correlation |

## Investigation Workflow

1. Reviewed QRadar offense activity
2. Correlated Windows authentication failure events
3. Validated endpoint telemetry in CrowdStrike
4. Performed endpoint validation through Tanium
5. Conducted IP attribution analysis using Infoblox
6. Determined activity aligned with legitimate service account validation behavior

   
## MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1110 | Brute Force |
| T1078 | Valid Accounts |
| T1087 | Account Discovery |
| T1046 | Network Service Discovery |
| T1071 | Application Layer Protocol |
Observed authentication failure activity initially aligned with potential brute-force and valid account abuse techniques. Cross-platform validation determined the activity was associated with legitimate internal service account validation behavior rather than malicious intrusion attempts.

## Key Findings

- Authentication failures originated from legitimate internal enterprise systems
- No malicious endpoint execution activity was identified in CrowdStrike or Tanium
- Windows Event ID 4776 activity aligned with NTLM authentication validation behavior
- Internal IP attribution matched known enterprise network segmentation
- No evidence of privilege escalation, brute-force compromise, or lateral movement was identified
- Activity was determined to be consistent with automated service account validation processes

## Skills Demonstrated

- SIEM Investigation & Offense Triage
- Cross-Platform Threat Correlation
- Authentication Failure Analysis
- Endpoint Detection & Response (EDR)
- Threat Hunting Methodology
- Windows Security Event Analysis
- Incident Validation & False Positive Reduction
- Network Attribution & IP Analysis
- Security Operations Center (SOC) Workflow Execution
- MITRE ATT&CK Mapping
- Enterprise Security Tool Correlation
- Investigative Documentation & Reporting
> Enterprise SOC investigation simulating real-world authentication anomaly triage across SIEM, EDR, endpoint validation, and network attribution platforms.

## Lessons Learned

This investigation reinforced the importance of validating authentication anomalies across multiple security platforms before escalating incidents. Correlating SIEM telemetry with endpoint and network attribution data reduced false positives and improved confidence in investigative conclusions.

## Screenshots

### QRadar Offense Overview
![QRadar](investigation-notes/screenshots/01-qradar-offense-overview.png.png)

### QRadar Event Correlation
![QRadar Correlation](investigation-notes/screenshots/02-qradar-event-correlation.png.png)

### CrowdStrike Validation
![CrowdStrike](investigation-notes/screenshots/03-crowdstrike-service-account-search.png.png)

### Tanium Endpoint Search
![Tanium](investigation-notes/screenshots/05-tanium-endpoint-search.png.png)

### Infoblox IP Search
![Infoblox](investigation-notes/screenshots/06-infoblox-ip-search.png.png)

### Infoblox Network Correlation
![Infoblox Correlation](investigation-notes/screenshots/07-infoblox-network-correlation.png.png)

## MITRE ATT&CK Mapping

| Technique | Description |
|------------|-------------|
| T1078 | Valid Accounts |
| T1110 | Brute Force |
| T1046 | Network Service Discovery |
| T1087 | Account Discovery |

Enterprise SOC Investigation Lab
QRadar | CrowdStrike | Tanium | Infoblox
