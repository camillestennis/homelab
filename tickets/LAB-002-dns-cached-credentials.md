# LAB-002: DNS misconfiguration hidden by cached credentials

| Field | Value |
|---|---|
| Category | DNS / Active Directory |
| Priority | High |
| Affected | WS01 |
| Status | Resolved |

## Reported symptom
<!-- TODO: describe what "the user" experienced, e.g. could log in but couldn't reach domain resources -->
User could still sign in to WS01, but domain services were not working.

## Troubleshooting
<!-- TODO: confirm and fill in the commands you actually ran and what each showed -->
1. Login succeeded, which made the domain look healthy
2. Checked WS01's DNS settings
3. Found it was not pointing at DC01, so it could not locate the domain controller

## Root cause
WS01's DNS was misconfigured. Windows cached credentials let the user log in anyway, which masked the problem.

## Resolution
<!-- TODO: how you corrected DNS -->
Pointed WS01's DNS back to DC01 and confirmed the client could locate the domain controller.

## Prevention / follow-up
Clients should get DNS from DHCP on DC01 rather than a manual setting.

## What I learned
A successful login doesn't prove the client can reach the domain controller. Cached credentials can hide a broken connection.
