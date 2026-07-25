# Troubleshooting Notes

## Issue 1

ShellBags registry keys not found.

### Cause

Folders were never opened using Windows Explorer.

### Resolution

Browse the folders through File Explorer before checking the registry.

---

## Issue 2

BagMRU appears empty.

### Cause

No folder navigation history exists.

### Resolution

Open several folders and nested directories.

---

## Issue 3

Deleted folder not visible in registry.

### Cause

Folder was deleted before being opened.

### Resolution

Open the folder first, then delete it.

---

## Issue 4

Registry path differs.

### Cause

Windows version differences.

### Resolution

Check:

HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\Shell

---

## Issue 5

Folder view settings not updated.

### Cause

Explorer settings not changed.

### Resolution

Switch between Details, Icons, or List view before reopening the registry.

---

## Issue 6

Recycle Bin empty.

### Cause

Folder permanently deleted.

### Resolution

Delete normally without using Shift+Delete.
