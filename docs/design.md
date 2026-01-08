## Input Handling

User data is imported via Import-UPUserData, which abstracts CSV and JSON input into PowerShell objects. This allows the provisioning logic to remain input-agnostic and simplifies future extensions.

## Logging

All operations are logged through a centralized Write-UPLog function.
This ensures consistent formatting, supports severity levels, and
simplifies future error handling and rollback mechanisms.

## Input Handling and Logging

The `Import-UPUserData` function is responsible for loading user data from external sources.
It abstracts input formats (CSV and JSON) and returns normalized PowerShell objects for downstream processing.

A centralized logging function (`Write-UPLog`) is used to ensure consistent, timestamped log entries.
Control flow was explicitly designed to avoid early returns during import, ensuring that successful
imports are logged before returning data to the caller.