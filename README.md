# DODINFWHOMI

This public repository packages two Lu Zu TAMP Obelisk reference kits and the supplied example output. These are research and inspection materials, not official DoD software.

## Contents

| Location | Description |
| --- | --- |
| [`kits/v2.0/`](kits/v2.0/README.md) | Windows PowerShell 5.1 kit and its accompanying files. |
| [`kits/v1.6/`](kits/v1.6/README.md) | PowerShell 7.6.6+ kit and its accompanying files. |
| [`releases/LuZu-TAMP-Obelisk-Zipper-Windows-PowerShell-5.1-v2.0-Kit.zip`](releases/LuZu-TAMP-Obelisk-Zipper-Windows-PowerShell-5.1-v2.0-Kit.zip) | Original v2.0 ZIP archive, copied unchanged. |
| [`releases/LuZu-TAMP-Obelisk-v1.6-With-README-Kit.zip`](releases/LuZu-TAMP-Obelisk-v1.6-With-README-Kit.zip) | Original v1.6 ZIP archive, copied unchanged. |
| [`examples/example-output.txt`](examples/example-output.txt) | Supplied sample output, included verbatim. |

Each kit retains the files and checksum manifest supplied with its archive. Read the version-specific README before using either kit; their runtime requirements and behavior differ.

## Example output

The example is provided as supplied; it was not generated or independently reproduced for this repository. Its reported `CMSAuthenticated` and `ManagementAuthorized` values are `False`, and its ADD/REMOVE counts are proposals only.

## Safety and scope

- The sample says the CMS containers were structurally parsed, but management signatures were **not authenticated**. Transport checks and CMS parsing do not establish DoD management authority, authorization, or subordination.
- The sample reports that no certificate add/remove/change operation was invoked for that run. The kits do not apply TAMP trust-anchor changes to Windows certificate stores; certificate catalogs are reference data, not instructions to trust or install every entry.
- Not every mode is read-only. `StoreAudit` reads certificate stores and may write a CSV report. Online retrieval and update modes contact configured endpoints and write local snapshots and logs, without applying certificate-store changes. The opt-in `EnableAutoUpdate` mode registers a daily current-user scheduled task; `DisableAutoUpdate` removes that task. These two modes change Windows Task Scheduler state and require the confirmation flags documented in each kit.
- Neither kit is DoD-certified or DoD-endorsed, neither replaces DoD InstallRoot, and this repository makes no claim of full DoD, STIG, or SCAP compliance.
- No license was supplied or added. Publication here does not grant reuse rights.

Review the relevant kit's source and documentation, and follow your organization's approval process, before running any script.
