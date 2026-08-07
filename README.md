# windows-dfir-lab43-bam-dam-investigation

## Overview

Background Activity Moderator (BAM) is a Windows feature that records recently executed applications in the SYSTEM registry hive. During digital forensic investigations, BAM provides valuable evidence of application execution, helping investigators reconstruct user activity even when other artifacts may be unavailable.

In this hands-on DFIR lab, BAM registry entries were examined using native Windows PowerShell. A custom executable was created and executed to generate application activity, after which BAM registry keys were analyzed to identify recently executed programs and understand how Windows stores execution evidence.

---

# Executive Summary

This investigation demonstrates how Windows BAM artifacts can be used to reconstruct application execution history without relying on third-party forensic software. By generating executable activity and examining BAM registry entries, the investigation successfully identified evidence of recently executed programs and validated BAM as a useful source of host-based forensic evidence.

The workflow mirrors a real-world DFIR investigation by creating activity, collecting registry evidence, correlating execution artifacts, and documenting findings.

---

# Investigation Objectives

- Understand the purpose of Windows BAM.
- Generate executable activity.
- Locate BAM registry keys.
- Examine BAM execution records.
- Identify recently executed applications.
- Correlate registry evidence with user activity.
- Document forensic findings.

---

# Skills Demonstrated

- Windows Registry Analysis
- BAM/DAM Artifact Investigation
- Windows DFIR Methodology
- Host-Based Forensics
- PowerShell Investigation
- Registry Evidence Collection
- Application Execution Analysis
- Artifact Correlation
- Evidence Documentation
- Incident Reporting

---

# Tools Used

- Windows 10
- Windows PowerShell
- Registry Provider (HKLM:)
- Command Prompt

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Investigation Type | Host-Based DFIR |
| Primary Artifact | BAM Registry |
| Analysis Method | Native Windows Tools |
| Shell | Windows PowerShell |
| Privileges | Administrator |

---

# Investigation Workflow

1. Create investigation workspace.
2. Generate executable activity.
3. Execute a custom application.
4. Navigate to the BAM registry key.
5. Enumerate BAM entries.
6. Correlate registry evidence.
7. Document findings.
8. Remove lab artifacts.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1059 | Command and Scripting Interpreter |
| T1083 | File and Directory Discovery |
| T1112 | Modify Registry |
| T1082 | System Information Discovery |

---

# Evidence Collected

- Investigation workspace
- Custom executable
- Executed application
- BAM registry entries
- Registry path information
- PowerShell outputs
- Cleanup verification

---

# Evidence Correlation

The investigation correlated multiple host artifacts to validate recent application execution.

- A custom executable was created and executed.
- BAM registry entries recorded executed applications.
- Registry values confirmed Windows maintained execution history.
- PowerShell successfully retrieved execution artifacts directly from the SYSTEM hive.

---

# Investigation Findings

The investigation confirmed that BAM maintains valuable evidence of recently executed applications within the Windows SYSTEM registry hive. Native PowerShell commands successfully identified BAM registry entries without requiring external forensic software, demonstrating how investigators can reconstruct user execution activity using built-in Windows capabilities.

---

# Key Takeaway

Windows BAM provides an important forensic artifact for identifying recently executed applications. Even when executable files are removed, BAM registry entries may still provide valuable evidence that helps investigators reconstruct user activity during DFIR investigations.
