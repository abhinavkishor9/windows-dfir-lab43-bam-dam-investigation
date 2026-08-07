# windows-dfir-lab43-bam-dam-investigation

## Overview

BAM stands for:

Background Activity Moderator

DAM stands for:

Desktop Activity Moderator

These are Windows features that monitor application activity to improve battery life and system performance.

Why Does Windows Use BAM/DAM?

Windows wants to know:

Which applications are running?
Which applications run in the background?
Which applications haven't been used recently?

This helps Windows:

Reduce unnecessary background activity.
Improve battery life.
Optimize system resources.

While doing this, Windows records information about executed programs.

Although they were designed for performance optimization, they also create valuable forensic evidence.
Imagine malware runs on a computer.

Later the attacker deletes:

the executable
shortcuts
temporary files

Even if the executable disappears, BAM may still contain a record showing that Windows executed it.

This makes BAM extremely useful for incident responders.

In this hands-on DFIR lab, BAM registry entries were examined using native Windows PowerShell. A custom executable was created and executed to generate application activity, after which BAM registry keys were analyzed to identify recently executed programs and understand how Windows stores execution evidence.

---

# Executive Summary

In this lab, we demonstrate examining BAM using PowerShell. We did not need to use a third-party software for this purpose. We created a custom executable and executed it. After that, we analyzed BAM Registry Keys using PowerShell.

---

# Investigation Objectives

- Locate the BAM Registry keys.
- Identify user SID entries.
- Generate executable activity.
- Enumerate BAM records using PowerShell.
- Identify recently executed programs.
- Correlate execution evidence.
- Document forensic findings.

---

# Tools Used

- Windows 10 VM
- PowerShell
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

- Investigation folder
- Custom executable DemoApp
- Executed application DemoApp
- BAM registry entries
- Registry path information
- PowerShell outputs

---

