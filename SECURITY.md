# Repository Safety

This is a public engineering portfolio, not a configuration vault.

## Never commit

- Passwords, PSKs, private keys, API tokens, SNMP community strings, or recovery codes
- Public IP addresses, serial numbers, support entitlement IDs, or full configuration exports
- Exact household addresses, floor plans with identifying detail, or unredacted screenshots
- Client names, hostnames, MAC addresses, email addresses, or browsing/traffic content

## Before publishing evidence

1. Replace identifiers with stable aliases such as `AP-1`, `CLIENT-A`, and `192.0.2.10`.
2. Crop screenshots to the relevant control or measurement.
3. Remove metadata where practical.
4. Prefer selected sanitized command output over raw backups.
5. Review staged changes for strings resembling keys, credentials, public addresses, or personal names.

Store recoverable production backups outside this repository in an encrypted location. A sanitized example is not a restorable backup.

## Safe testing boundary

Capture and test only traffic and systems owned by or explicitly authorized for this lab. Do not deauthenticate clients, intercept credentials, attack neighboring networks, or create intentional production disruption.
