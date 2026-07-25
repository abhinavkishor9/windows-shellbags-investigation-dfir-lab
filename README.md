# windows-shellbags-investigation-dfir-lab
## Overview

Windows Explorer stores folder navigation information inside **ShellBags**, a registry artifact that records folders viewed by a user—even if those folders are later renamed or deleted.

Unlike Recent Files or Jump Lists, ShellBags primarily reveal **folder activity**, making them valuable during Digital Forensics and Incident Response (DFIR) investigations.

This lab demonstrates how Windows preserves evidence of user folder access using native Windows artifacts.

---

# Executive Summary

During this investigation a controlled Windows environment was created containing multiple directories representing Finance, HR, and Projects.

The analyst:

- Created several folders and nested directories
- Opened folders using Windows Explorer
- Modified Explorer view settings
- Deleted one folder
- Examined ShellBag registry artifacts

The investigation demonstrates that Windows retains evidence of folder browsing behavior even after directories are removed from disk.

---

# Investigation Objectives

- Understand Windows ShellBag artifacts
- Identify registry locations storing folder history
- Observe persistence after folder deletion
- Correlate deleted folders with existing registry entries
- Understand DFIR value of ShellBags

---

# Lab Environment

| Component | Details |
|------------|---------|
| OS | Windows 10 x64 |
| Virtualization | VMware Workstation Player |
| User | Dell |
| Registry Tool | Windows Registry Editor |
| Command Line | Windows PowerShell |
| File Explorer | Windows Explorer |

---

# Tools Used

- Windows Registry Editor
- Windows Explorer
- PowerShell
- Command Prompt

---

# MITRE ATT&CK Mapping

Although ShellBags are not a persistence mechanism themselves, they are valuable forensic artifacts during post-compromise investigations.

| Technique | ID |
|-----------|----|
| File and Directory Discovery | T1083 |
| Data from Local System | T1005 |
| Indicator Removal (Deleted folders still recoverable through artifacts) | T1070 |
| File and Directory Discovery (Forensic Reconstruction) | T1083 |

---

# Skills Demonstrated

- Windows Registry Analysis
- Registry Artifact Identification
- Windows Explorer Forensics
- ShellBag Artifact Analysis
- Folder Activity Reconstruction
- User Activity Timeline Building
- Deleted Folder Investigation
- Registry-Based DFIR
- Evidence Correlation
- Windows Forensic Documentation

---

# Lab Scenario

An analyst receives a workstation suspected of containing sensitive project documents.

The user claims several folders were deleted before handing over the system.

The objective is to determine:

- Which folders were accessed
- Which folders still exist
- Which folders were deleted
- Whether registry artifacts preserve historical evidence

---

# Evidence Collected

- ShellBag registry keys
- BagMRU registry hierarchy
- Explorer folder view configuration
- Deleted folder evidence
- Sample directory structure
- PowerShell commands
- Registry screenshots

---

# Evidence Correlation

The investigation correlated multiple evidence sources:

- Folder structure created during the lab
- Windows Explorer navigation history
- ShellBag registry entries
- BagMRU hierarchy
- Deleted folder (ThreatHunting)
- Recycle Bin evidence

Although the folder no longer existed, Windows retained historical metadata inside the registry, demonstrating the forensic value of ShellBags.

---

# Investigation Findings

The analysis confirmed that:

- Windows records folder navigation history inside ShellBags.
- Nested folders generate additional BagMRU entries.
- Folder view changes (Details, Icons, etc.) are preserved.
- Deleted folders may still be referenced within registry artifacts.
- ShellBags provide valuable evidence for reconstructing user behavior.

---

# Key Takeaway

ShellBags provide investigators with a persistent record of folder access and navigation. Even when directories are deleted, registry artifacts often remain, allowing analysts to reconstruct user activity and support forensic investigations.
