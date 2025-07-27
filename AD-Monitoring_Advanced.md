## Advanced Active Directory Monitoring

This file outlines advanced techniques for monitoring Active Directory environments in a Security Operations Center.

### 1. SID History Injection
Technique: T1134.005 SID History Abuse  
Log source: Event ID 4742 (user account changes)  
Pattern: SID history attribute set or modified  
Look for: Addition of privileged SIDs (such as Domain Admin SID) in SIDHistory

### 2. Golden Ticket Detection
Technique: T1558.001 Kerberoasting or Ticket Forging  
Log source: Event ID 4769 (Kerberos service ticket request) and 4624 (logon events)  
Pattern: Unusual or non-existent user requesting TGT  
Look for: High ticket lifetime, anomalies in encryption type, or use of RC4 encryption

### 3. Skeleton Key Attack
Technique: Credential Manipulation  
Log source: LSASS memory and Event ID 4624  
Pattern: Multiple successful logons without failed attempts  
Look for: Same account logging in to multiple systems with a generic password

### 4. DC Shadow Attack
Technique: T1207 DCShadow  
Log source: Event ID 5137, 4662, 4929  
Pattern: Rogue Domain Controller registration and replication behavior  
Look for: Unusual changes in replication metadata or new DC objects

### 5. AdminSDHolder Abuse
Technique: Persistence via AdminSDHolder  
Log source: Event ID 4662 (object access), 4732 (admin group membership)  
Pattern: Changes to AdminSDHolder object or its ACL  
Look for: ACLs granting excessive privileges outside of normal changes

### 6. Unauthorized Replication Requests
Technique: T1003.006 DCSync  
Log source: Event ID 4662 (Directory Service Access)  
Pattern: Access to replication permissions (DS-Replication-Get-Changes)  
Look for: Non-DC accounts using replication privileges

### 7. NTDS.dit Access Monitoring
Technique: T1003 Credential Dumping  
Log source: File access logs or Sysmon Event ID 10  
Pattern: Access to NTDS.dit or SYSTEM hive  
Look for: Unexpected access outside backup windows

### 8. Anomalous Kerberos Ticket Volume
Technique: T1558.003 Overpass-the-Hash  
Log source: Event ID 4769, 4770, 4771  
Pattern: High frequency of service ticket requests  
Look for: Ticket volume spikes correlated with the same user or host

### 9. Group Policy Tampering
Technique: T1484.001 GPO Abuse  
Log source: Event ID 5136 (Directory object change), 4688 (process creation)  
Pattern: Modification of GPO settings outside approved change windows  
Look for: Unexpected user rights assignments or logon scripts

### 10. Domain Trust Abuse
Technique: T1484.002 Domain Trust Modification  
Log source: Event ID 4716 (trust creation), 4742 (user changes), 5136  
Pattern: Changes to trust relationships or transitive trust paths  
Look for: Unauthorized addition of external trusts

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
