# Investigation Notes

## Lab Summary

This investigation focused on analyzing Windows Background Activity Moderator (BAM) registry artifacts using native PowerShell.

The investigation reconstructed recent application execution by generating executable activity and examining BAM registry entries stored within the SYSTEM hive.

---

## Analyst Methodology

1. Create investigation workspace.
2. Create a custom executable.
3. Execute the application.
4. Navigate to the BAM registry key.
5. Enumerate BAM UserSettings.
6. Review execution entries.
7. Correlate executable activity.
8. Document findings.
9. Clean up lab artifacts.

---

## Investigation Scenario

Suppose malware is suspected.

Investigators discover:

- The malicious executable has already been deleted.
- No Prefetch evidence is available.
- Process execution logs are incomplete.

Questions:

- Was the executable recently executed?
- Which applications were recently run?
- Can the SYSTEM registry provide execution evidence?

The investigation uses BAM registry artifacts to reconstruct recent application execution.

---

## Evidence Collected

### Evidence 1 – Investigation Workspace

Collected:

- C:\BAMLab

Finding:

Established investigation workspace.

---

### Evidence 2 – Executable Activity

Collected:

- DemoApp.exe
- Application execution

Finding:

Generated execution activity for analysis.

---

### Evidence 3 – BAM Registry

Command Used

```powershell
Get-ChildItem "HKLM:\SYSTEM\CurrentControlSet\Services\bam\State\UserSettings"
```

Finding:

Enumerated available BAM registry entries.

---

### Evidence 4 – Registry Properties

Command Used

```powershell
Get-ItemProperty "HKLM:\SYSTEM\CurrentControlSet\Services\bam\State\UserSettings\<SID>"
```

Finding:

Displayed recorded executable paths.

---

## DFIR Analysis

The investigation demonstrated how BAM registry artifacts preserve evidence of recently executed applications.

Even without specialized forensic software, PowerShell provided sufficient visibility into BAM entries to validate application execution history.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | Command and Scripting Interpreter | T1059 |
| Discovery | File and Directory Discovery | T1083 |
| Defense Evasion | Modify Registry | T1112 |

---

## Analyst Observations

- BAM stores execution information inside the SYSTEM registry hive.
- PowerShell can enumerate BAM entries without external tools.
- Execution artifacts remain useful for reconstructing user activity.
- Registry artifacts complement other execution evidence such as Prefetch and Amcache.
- Multiple forensic artifacts improve investigation confidence.

---

## Conclusion

The investigation demonstrated how Windows BAM registry artifacts can be used to identify recently executed applications using native Windows tools while emphasizing evidence collection, registry analysis, artifact correlation, and structured DFIR documentation.
