# HTTP Parameter Tampering

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate whether the application securely
validated user-controlled parameters submitted during authentication.

## Vulnerability Identified

The application trusted client-controlled parameters contained within
an HTTP POST request.

By modifying these parameters before the request reached the server,
it was possible to influence the application's authentication and
authorization behaviour.

## Investigation

I submitted the application's login form and used Firefox Developer
Tools to inspect the resulting HTTP POST request.

The request contained multiple user-controlled parameters associated
with authentication and user identification.

I modified selected parameters using the browser's request editing and
resending functionality.

The server accepted the modified request, demonstrating that sensitive
authorization decisions were being influenced by client-controlled
values without sufficient server-side validation.

## Security Impact

Improper validation of client-controlled parameters may allow an
attacker to:

- Manipulate user identifiers
- Circumvent intended access controls
- Impersonate another user
- Access functionality intended for more privileged accounts

## Root Cause

The application relied on values supplied by the client when making
security-sensitive decisions.

Client-controlled data should never be trusted without appropriate
server-side validation and authorization checks.

## Mitigation

Applications should:

- Validate all user-controlled input on the server
- Perform authorization checks independently of client-supplied values
- Derive user identity from authenticated server-side session data
- Prevent users from controlling security-sensitive identifiers
- Apply least-privilege access controls

## Skills Demonstrated

- HTTP request analysis
- Firefox Developer Tools
- POST request inspection
- Parameter tampering
- Authentication testing
- Access-control analysis
- Web vulnerability assessment
- Security remediation

## Result

The weakness was successfully identified and demonstrated within the
authorised academic laboratory environment.

Challenge secrets, credentials, internal URLs and assessment-specific
values have intentionally been excluded from this public repository.

## Ethical & Academic Context

All testing documented here was performed within an authorised
university cybersecurity laboratory.

No external or third-party systems were targeted.
