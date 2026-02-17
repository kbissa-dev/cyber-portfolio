# Detection

This folder contains simple detection ideas and queries (Splunk SPL / Sentinel KQL) mapped to common attacker behaviour.

## Convention 
Use: 'YYYY-MM-DD_detection-name.md'

## Each detection file should include 
#### Goal
What you are trying to detect

### Data source
What logs are required (e.g., AZure AD sign-in logs, Windows Security logs, VPN logs, DNS, proxy).

### Query / Rule
Paste the SPL/KQL and explain the key fields.

### Tuning notes
- What could cause false positives
- How you would reduce noise (thresholds, allowlists, exclusions)

### Severity Suggestion
Low / Medium / High + why.

### MITRE mapping
Technique + short reason.

## Note
Keep detection realistic and testable. A small rule that works is better than a fancy rule that doesn't.
