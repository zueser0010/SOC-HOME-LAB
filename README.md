Privilege Escalation Detection

## Overview
Simulated and detected a full privilege escalation 
attack on Windows 10 using Wazuh SIEM.

## Environment
| Machine | Role | IP |
|---------|------|----|
| Kali Linux | Attacker | 192.168.10.144 |
| Windows 10 | Target | 192.168.10.120 |
| Ubuntu (Wazuh) | SIEM | 192.168.10.148 |

## Attack Performed
1. Created backdoor user account
2. Added account to Administrators group
3. Assigned special privileges

## Detection — Wazuh Alerts

| Event ID | Description | Wazuh Rule | Level |
|----------|-------------|------------|-------|
| 4720 | New user account created | 60109 | 8 |
| 4672 | Special privileges assigned | 60106 | 3 |
| 4732 | User added to Admins group | 60114 | 10 |

## MITRE ATT&CK Mapping

| Technique | ID | Description |
|-----------|-----|-------------|
| Create Account | T1136 | Backdoor account created |
| Account Manipulation | T1098 | Added to admin group |
| Privilege Escalation | T1068 | Admin privileges gained |

## Evidence


![Event 4720](../event_4720%20account%20created.jpeg)




![MITRE Mapping](../mitre%20attack%20mapping.jpeg)




![Timestamp](../timestamp.jpeg)




![Wazuh Dashboard](../wazuh%20agent%20dashboard.jpeg)



## Recommendations
1. Enable account lockout policies
2. Monitor Event ID 4720 and 4732 in real time
3. Alert on any new administrator account creation
4. Implement least privilege across all accounts
