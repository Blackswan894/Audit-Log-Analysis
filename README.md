# Audit-Log-Analysis
This project demonstrates how Linux Auditd can monitor and log changes made to protected system files.   By setting up audit rules and simulating attacks, the goal was to identify which files were altered, determine which attack caused each change, and analyze how Auditd captured those events.

Auditd helps system administrators and cybersecurity analysts monitor critical system events by logging any file access, modification, or deletion performed by users or processes. Through these logs, investigators can determine who made a change, when it occurred, and which process was responsible.

Methodology

1. Monitored File Changes:
   Audit rules were configured to watch specific files within the `/protected_files/` directory.

2. Triggered Simulated Attacks:
   Various attack scenarios (attack-a, attack-b, and attack-c) were executed to test Audit’s ability to detect and log unauthorized modifications.

3. Analyzed Audit Logs: 
   Using `ausearch` and `aureport`, the log entries were reviewed to identify which attacks altered which files.  
   Each event was correlated with the responsible process ID (PID), user, and timestamp.


Affected Files

The following files were targeted during the simulation:

- `cloudia.txt`  
- `oakley.txt`  
- `squeaky.txt`  
- `precipitation.csv`

Attack Mapping

| File Path | Attack Type |
|------------|--------------|
| `/protected_files/cloudia.txt` | attack-a |
| `/protected_files/oakley.txt` | attack-b |
| `/protected_files/squeaky.txt` | attack-b |
| `/protected_files/precipitation.csv` | attack-c |

Results & Insights

- Auditd successfully detected all modifications and accurately logged the users and timestamps associated with each attack.  
- The attack mapping table demonstrates how log data can be used to reconstruct events and verify file integrity.  
- This project highlights the importance of file auditing in incident response and forensic investigations.
Key Takeaways
- Linux Auditd is a powerful tool for monitoring system integrity.  
- Proper configuration of audit rules enables real-time detection of file tampering.  
- Logs provide crucial evidence for identifying malicious activity and strengthening system defenses.

