# Investigation Notes

## Investigation Information

**Lab:** Windows ShellBags Investigation

**Investigation Type:** Registry Artifact Analysis

**Platform:** Windows 10

**Artifact:** ShellBags

---

# Lab Summary

The objective of this investigation was to analyze Windows ShellBag registry artifacts generated after creating, opening, modifying, and deleting directories.

The exercise demonstrates how Windows Explorer stores folder navigation metadata independently of the file system.

---

# Analyst Methodology

The investigation followed a structured DFIR workflow:

1. Prepare a controlled directory structure.
2. Generate user interaction by browsing folders.
3. Modify Explorer folder view settings.
4. Delete one directory to simulate user cleanup.
5. Inspect ShellBag and BagMRU registry locations.
6. Correlate registry artifacts with observed user activity.
7. Document forensic findings and persistence of evidence.

---

# Investigation Steps

## Step 1

Created investigation directory:

C:\ShellBagsLab

---

## Step 2

Created folders:

Finance

HR

Projects

Projects\IncidentResponse

Projects\ThreatHunting

---

## Step 3

Created sample files.

Payroll.xlsx

Employees.txt

IOC_List.txt

---

## Step 4

Opened folders using Windows Explorer.

---

## Step 5

Changed folder view.

Example:

Details View

Large Icons

---

## Step 6

Deleted:

ThreatHunting

---

## Step 7

Opened Registry Editor.

Visited:

HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\Shell\BagMRU

and

HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\Shell\Bags

---

# Evidence Collected

- Folder hierarchy
- Deleted directory
- BagMRU registry entries
- ShellBag registry values
- Folder view metadata
- Recycle Bin entry
- Registry screenshots

---

# Findings

Observed:

✓ Folder navigation recorded

✓ Nested directories created additional BagMRU entries

✓ Folder view preferences stored

✓ Deleted folder evidence remained available

---

# Analyst Observations

The ShellBag registry keys retained information about folder browsing activity even after the **ThreatHunting** folder was deleted.

The **BagMRU** hierarchy reflected the nested folder structure created during the lab, while the **Bags** registry key stored Explorer view settings such as icon size and display mode. This demonstrates that ShellBags capture both navigation history and user interface preferences.

These artifacts can help investigators reconstruct user behavior even when folders no longer exist on disk, making them valuable during incident response and post-compromise forensic analysis.

---

# Conclusion

ShellBags provide reliable evidence of Windows Explorer activity and remain one of the most valuable registry artifacts for reconstructing historical folder access.
