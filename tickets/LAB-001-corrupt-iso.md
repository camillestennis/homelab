# LAB-001: OPNsense install failing from a corrupt ISO

| Field | Value |
|---|---|
| Category | Build / file integrity |
| Priority | Medium (blocked lab build) |
| Affected | FW01 |
| Status | Resolved |

## Reported symptom
The OPNsense installer would not complete when building FW01.

## Troubleshooting
<!-- TODO: confirm these steps match what you did, and add the exact error you saw -->
1. Compared the downloaded ISO's SHA-256 hash against the checksum published by OPNsense
2. Hashes did not match, confirming the file was corrupt rather than a VM config problem

## Root cause
Corrupt ISO download.

## Resolution
Re-downloaded the image, verified the SHA-256 hash matched, and completed the install.

## Prevention / follow-up
Verify the checksum on every installer before uploading it to Proxmox.

## What I learned
Check the simplest layer first. A hash check takes seconds and rules out the source file before spending time on VM settings.
