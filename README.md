#  Privilege Escalation Detection

## Lab Overview
Simulated and detected privilege escalation
attack on Windows 10 using Wazuh SIEM.

## Environment
| Machine | Role | IP |
|---------|------|----|
| Kali Linux | Attacker | 192.168.10.100 |
| Windows 10 | Target | 192.168.10.145 |
| Wazuh | SIEM | 192.168.10.148 |

## Attack Performed
- Created backdoor admin account
- Added to Administrators group
- Special privileges assigned

## Events Detected
| Event ID | Description | Severity |
|----------|-------------|----------|
| 4720 | New user account created | High |
| 4672 | Special privileges assigned | High |
| 4732 | Added to admin group | High |

## MITRE ATT&CK Mapping
| Technique | Description |
|-----------|-------------|
| T1098 | Account Manipulation |
| T1484 | Defense Evasion |
| T1136 | Create Account |

## Key Learnings
- How privilege escalation appears in Windows logs
- How Wazuh maps events to MITRE ATT&CK
- How to detect backdoor account creation
- Importance of monitoring Event IDs
