# PowerShell User Provisioning

## Importing User Data

User data is imported using the `Import-UPUserData` function, which supports both CSV and JSON input formats.
The function performs the following steps:

1. Logs the start of the import operation.
2. Verifies that the input file exists.
3. Determines the file format based on file extension.
4. Imports the data into PowerShell objects.
5. Logs the number of user records successfully imported.
6. Returns the imported user objects to the caller.

All import operations are wrapped in structured error handling. Any failure during the import process
is logged with severity `ERROR` and re-thrown to ensure upstream functions can handle rollback or termination.

## Workflow
1. Import user data from CSV or JSON (`Import-UPUserData`)
2. Validate required user attributes (`Test-UPUserData`)
3. Simulate provisioning actions (`Invoke-UPProvisioning`)
4. Enable real provisioning in later stages

Import-UPUserData → Test-UPUserData → Invoke-UPProvisioning