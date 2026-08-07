# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 07:05 | Created investigation workspace | C:\BAMLab |
| 07:08 | Created DemoApp.exe | DemoApp.exe |
| 07:10 | Executed DemoApp.exe | Start-Process |
| 07:15 | Navigated to BAM registry | Registry Provider |
| 07:20 | Enumerated UserSettings | Get-ChildItem |
| 07:25 | Retrieved BAM registry values | Get-ItemProperty |
| 07:30 | Correlated executable activity | Registry Evidence |
| 07:35 | Removed investigation artifacts | Remove-Item |

---

# Investigation Flow

Investigation Started

↓

Created Investigation Workspace

↓

Created DemoApp.exe

↓

Executed Application

↓

Navigated to BAM Registry

↓

Enumerated UserSettings

↓

Reviewed Registry Entries

↓

Correlated Execution Evidence

↓

Documented Findings

↓

Cleaned Up Lab

↓

Investigation Completed

---

# Summary

The investigation reconstructed recent application execution using Windows Background Activity Moderator (BAM) registry artifacts. Native PowerShell commands successfully enumerated BAM entries from the SYSTEM registry hive, demonstrating how investigators can identify recently executed applications, correlate registry evidence, and document host-based forensic findings without relying on third-party forensic software.
