# Active Directory SOC Monitoring Guide

This guide provides a structured approach to monitoring Active Directory from a SOC perspective. It begins with basic hygiene and moves toward advanced detection. Each section includes the attack technique, relevant event IDs, and detection logic.

---

## 1. Account Creation
Technique: New user creation  
Log source: 4720  
Pattern:  
- Accounts created outside standard working hours  
- Created by non-admin users  
- Immediately followed by group membership changes

---

## 2. Privilege Escalation
Technique: Unauthorized group membership changes  
Log source: 4728 4729 4732 4733  
Pattern:  
- Users added to Domain Admins or other high-privilege groups  
- Group additions and removals within short timeframes  
- Modified by unknown or non-standard admin accounts

---

## 3. SID History Injection
Technique: T1134.005 SID History Abuse  
Log source: 4742  
Pattern:  
- SID history attribute modified  
- Injected SID matches privileged groups like Domain Admins

---

## 4. Kerberoasting
Technique: T1558.003 Kerberoasting  
Log source: 4769  
Pattern:  
- Service ticket requests for accounts with ServicePrincipalName set  
- RC4 encryption used for ticket  
- High volume of requests in short time

---

## 5. Golden Ticket Attack
Technique: T1558.001 Golden Ticket  
Log source: 4768 4769 4624  
Pattern:  
- Ticket granting ticket created for non-existent or disabled user  
- Unusual lifetime on ticket  
- Logons from unexpected devices or IPs

---

## 6. Pass the Ticket
Technique: T1550.003 Pass the Ticket  
Log source: 4624 4672 4769  
Pattern:  
- Logons using Kerberos tickets from unfamiliar hosts  
- Admin logon from workstation not assigned to admin  
- No prior interactive logon from source

---

## 7. Pass the Hash
Technique: T1550.002 Pass the Hash  
Log source: 4624 4625  
Pattern:  
- Type 3 logons using NTLM from new or suspicious hosts  
- Success after multiple failed attempts  
- No accompanying password change or reset

---

## 8. DC Sync Attack
Technique: T1003.006 DCSync  
Log source: 4662  
Pattern:  
- Access to DS-Replication-Get-Changes or similar rights  
- Access granted to non-standard accounts  
- Access attempts from non-DC systems

---

## 9. DC Shadow Attack
Technique: T1003.006 DCShadow  
Log source: 5136  
Pattern:  
- NTDS settings object modified  
- Attribute changes by non-DC host  
- Unexpected changes to replication metadata

---

## 10. Logon Anomalies
Technique: Lateral movement via stolen credentials  
Log source: 4624 4625  
Pattern:  
- Type 3 and Type 10 logons from unusual systems  
- High frequency logons from single source  
- Failed logon attempts preceding success

---

## 11. AdminSDHolder Abuse
Technique: Privilege persistence  
Log source: 4662  
Pattern:  
- Modifications to AdminSDHolder container  
- Changes made by non-admins  
- Delegation changes to protected groups

---

## 12. Enumeration
Technique: T1087.002 Account Discovery  
Log source: 4661  
Pattern:  
- High volume access to directory objects  
- Access to attributes like memberof or logonHours  
- Enumeration from single workstation over short time

---

## 13. Group Policy Abuse
Technique: T1484.001 GPO Abuse  
Log source: 4739 5141  
Pattern:  
- GPO linked or modified targeting critical systems  
- Executable paths or scripts modified  
- GPO applied from unfamiliar source

---

## 14. Object Access Monitoring
Technique: Object-level access audit  
Log source: 4660 4663  
Pattern:  
- Sensitive object access like SYSVOL or NTDS.dit  
- Access by non-service or user accounts  
- Audit logs cleared or overwritten

---

## 15. Security Setting Changes
Technique: Defense evasion  
Log source: 4739 4907 4719  
Pattern:  
- Auditing policy disabled or modified  
- Removal of security logs  
- Group policy settings reverted

---

## 16. User Account Lockouts
Technique: Brute force detection  
Log source: 4740  
Pattern:  
- Multiple lockouts in short duration  
- Targets include admin or service accounts  
- Originating IP or workstation unfamiliar

---

## 17. Credential Dumping
Technique: T1003 LSASS Memory Dump  
Log source: Sysmon Event ID 10  
Pattern:  
- Access to lsass.exe by non-standard processes  
- Tools like procdump or taskmgr  
- Execution from non-administrative terminal

---

## 18. Scheduled Task Abuse
Technique: Persistence  
Log source: 4698 4702  
Pattern:  
- New tasks created by user accounts  
- Tasks configured to run tools or scripts  
- Scheduled to execute at odd hours

---

## 19. Remote WMI Execution
Technique: Remote command execution  
Log source: 4688 5861 (if WMI auditing enabled)  
Pattern:  
- WMI consumer binding by non-admin  
- WMI execution from endpoint not in admin network  
- Unexpected process launched through WMI

---

## 20. Security Log Tampering
Technique: Log clearing  
Log source: 1102  
Pattern:  
- Security log cleared  
- Cleared by interactive user not part of SOC  
- Followed by other suspicious activity

---

## Operational Notes
- Always correlate across multiple log types  
- Maintain baselines for normal account behavior  
- Ingest logs into SIEM with normalization  
- Use alerting with suppression for known patterns  
- Investigate anomalies even if no alert fires

---

## References

### Official Microsoft Docs

- Windows Security Auditing Event IDs  
  https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/basic-audit-events

- Advanced Auditing Policies  
  https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/advanced-security-auditing

- Security Monitoring Recommendations  
  https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/security-monitoring-recommendations

- Event ID Glossary  
  https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/event-id

### MITRE ATTACK Enterprise Windows

- Active Directory Techniques  
  https://attack.mitre.org/techniques/enterprise/

- Privilege Escalation Techniques  
  https://attack.mitre.org/tactics/TA0004/

- Credential Access  
  https://attack.mitre.org/tactics/TA0006/



