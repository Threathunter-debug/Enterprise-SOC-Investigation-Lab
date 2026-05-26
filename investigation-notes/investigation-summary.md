# Enterprise SOC Investigation Summary

## Investigation Overview

This investigation simulates a real-world enterprise SOC workflow involving authentication failure analysis, endpoint validation, IP attribution, and cross-platform event correlation.

The objective was to determine whether repeated authentication failures were associated with malicious activity, lateral movement, or internal service account validation behavior.

---

## Technologies Utilized

| Technology | Purpose |
|---|---|
| IBM QRadar | SIEM event correlation and alert triage |
| CrowdStrike Falcon | Endpoint detection and validation |
| Tanium | Endpoint visibility and asset validation |
| Infoblox | IP attribution and subnet correlation |

---

# Investigation Workflow

## 1. QRadar Offense Review

### Actions Performed
- Reviewed authentication failure offense activity
- Validated source and destination relationships
- Correlated internal authentication patterns
- Reviewed timestamps and event sources

### Findings
Authentication failures were observed across multiple internal systems and appeared consistent with automated service account validation behavior rather than malicious login attempts.

![QRadar Offense Overview](screenshots/01-qradar-offense-overview.png)

---

## 2. QRadar Event Correlation

### Actions Performed
- Reviewed correlated events tied to the offense
- Validated authentication behavior consistency
- Investigated source-to-destination activity flow

### Findings
No evidence of brute-force behavior, privilege escalation, or suspicious authentication anomalies was identified.

![QRadar Event Correlation](screenshots/02-qradar-event-correlation.png)

---

## 3. CrowdStrike Endpoint Validation

### Actions Performed
- Searched for endpoint detections
- Reviewed process execution activity
- Investigated suspicious indicators

### Findings
No malicious endpoint activity or suspicious execution behavior was identified during endpoint validation.

![CrowdStrike Validation](screenshots/03-crowdstrike-service-account-search.png)

---

## 4. Tanium Endpoint Validation

### Actions Performed
- Verified endpoint visibility
- Confirmed asset inventory presence
- Investigated endpoint artifacts

### Findings
The endpoint was successfully validated within the enterprise environment with no evidence of suspicious artifacts or persistence mechanisms.

![Tanium Endpoint Validation](screenshots/04-tanium-endpoint-search.png)

---

## 5. Infoblox IP Attribution

### Actions Performed
- Performed subnet ownership validation
- Investigated DHCP/network attribution
- Correlated IP ownership information

### Findings
The IP address was confirmed as internally owned infrastructure associated with enterprise network operations.

![Infoblox IP Search](screenshots/05-infoblox-ip-search.png)

---

## 6. Infoblox Network Correlation

### Actions Performed
- Validated internal network ownership
- Correlated subnet allocation
- Reviewed network attribution details

### Findings
Network attribution aligned with legitimate internal enterprise infrastructure and known organizational network segmentation.

![Infoblox Correlation](screenshots/06-infoblox-ip-correlation.png)

---

# Investigation Conclusion

No malicious endpoint activity was identified during the investigation.

Authentication failures appeared consistent with internal service account validation activity across multiple enterprise systems.

Cross-platform validation utilizing QRadar, CrowdStrike Falcon, Tanium, and Infoblox did not identify evidence of:
- Endpoint compromise
- Lateral movement
- Malicious persistence
- Credential abuse
- Suspicious process execution

The activity was ultimately classified as legitimate internal authentication behavior and a false positive security event.

---

# Skills Demonstrated

- SIEM Investigation
- QRadar Event Correlation
- Threat Hunting
- Endpoint Detection & Response (EDR)
- CrowdStrike Falcon Analysis
- Tanium Asset Validation
- Infoblox IP Attribution
- False Positive Analysis
- Cross-Platform Security Investigation
- MITRE ATT&CK Aligned Investigation
- SOC Alert Triage
- Security Event Documentation
