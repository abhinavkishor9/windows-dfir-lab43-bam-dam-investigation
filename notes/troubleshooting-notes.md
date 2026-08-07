# Troubleshooting Notes

## Issue 1

BAMLab folder already existed.

### Cause

Previous lab artifacts were still present.

### Resolution

Remove the existing folder before starting.

```powershell
Remove-Item C:\BAMLab -Recurse -Force
```

---

## Issue 2

Unable to locate BAM registry key.

### Cause

Incorrect registry path.

### Resolution

Navigate to:

```powershell
HKLM:\SYSTEM\CurrentControlSet\Services\bam\State\UserSettings
```

---

## Issue 3

Only registry values appeared as byte arrays.

### Cause

BAM stores execution metadata in binary format.

### Resolution

Use:

```powershell
Get-ItemProperty
```

to enumerate executable paths and values.

---

## Issue 4

DemoApp.exe did not appear immediately.

### Cause

BAM updates are not always instantaneous.

### Resolution

Execute the application again and re-query the registry.

---

## Issue 5

Expected external parser could not run.

### Cause

AppCompatCacheParser required the .NET Desktop Runtime.

### Resolution

Continue the investigation using native PowerShell registry analysis.

---

## Issue 6

Cleanup verification required.

### Cause

Investigation artifacts remained after the lab.

### Resolution

Delete the investigation folder.

```powershell
Remove-Item C:\BAMLab -Recurse -Force
```
