# Reclaim, releases

Downloads for [Reclaim](https://reclaim.orchestiq.com), a Windows disk tool that
reports the bytes a cleanup would really return rather than logical file sizes,
and tells you what each removal costs to undo.

**This repository holds releases and nothing else.** There is no source here. The
source is private.

## Download

Latest build on [Releases](../../releases). Windows 10 or 11, x64. Free for
personal use.

- **Portable ZIP.** Unpack it and run `reclaim.exe`. Nothing is installed and
  deleting the folder removes every trace.
- **MSI installer.** An ordinary Windows install with a Start menu entry, and
  the only one of the two that can update itself.

Windows SmartScreen will warn about an unrecognised publisher, because these
builds are not code signed yet. That warning is about the absence of a
certificate, not about anything found in the file.

## Verifying a download

Every release lists SHA-256 hashes. Check one before running it:

```powershell
Get-FileHash .\Reclaim_x64_en-US.msi -Algorithm SHA256
```

Updates are separately signed with a key that never leaves the build machine,
and the application refuses any update whose signature does not verify. That
signature is not an Authenticode certificate and does nothing about the
SmartScreen warning above.

## Reporting something

Open an [issue](../../issues). The useful ones say which drive, what Reclaim
claimed, and what actually happened. A rule that classifies something wrongly is
worth reporting even when nothing was deleted, because the classification is the
part that decides what gets offered.
