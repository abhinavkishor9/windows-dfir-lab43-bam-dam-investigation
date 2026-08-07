# Investigation Notes

## Lab Summary

In this lab, we focused on analyzing BAM Artifacts using PowerShell.

We generated executable activity by creating and executing a custom executable. Then, we examined BAM registry entries stored within the SYSTEM hive.

---

## Analyst Methodology

1. Create investigation folder.
2. Create a custom executable.
3. Execute the application.
4. Navigate to the BAM registry key.
5. Enumerate BAM UserSettings.
6. Review execution entries.

---

## Investigation Scenario

Suppose an analyst receives an alert:

Malware executed yesterday.

The executable has already been deleted.

Questions:

Was it really executed?
Which user launched it?
When was it executed?

BAM may still contain the executable path and its last execution time.


---

## Evidence Collected

### Evidence 1 – Investigation Folder created

Collected:

- C:\BAMLab

Finding:

Established investigation workspace.

---

### Evidence 2 – Executable Activity using custom executable

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



## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | Command and Scripting Interpreter | T1059 |
| Discovery | File and Directory Discovery | T1083 |
| Defense Evasion | Modify Registry | T1112 |

---

