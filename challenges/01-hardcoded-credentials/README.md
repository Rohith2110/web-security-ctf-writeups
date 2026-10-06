# Hardcoded Credentials in Client-Side JavaScript

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate the application's authentication
mechanism and identify security weaknesses that could expose sensitive
information.

## Vulnerability Identified

The application contained authentication credentials directly within
client-side JavaScript.

Because JavaScript delivered to a user's browser can be inspected using
browser developer tools, sensitive credentials should never be stored
within client-side source code.

## Investigation

I used Firefox Developer Tools to inspect the JavaScript resources loaded
by the application.

I navigated to the authentication-related JavaScript file and reviewed
the client-side code.

During the analysis, I identified authentication credentials embedded
within the JavaScript.

Using the exposed credentials demonstrated that sensitive authentication
information available within client-side code could lead to unauthorised
access.

## Security Impact

Hardcoded credentials within client-side resources can potentially allow
an attacker to:

- Obtain authentication credentials
- Bypass intended authentication controls
- Gain unauthorised access to protected functionality
- Reuse exposed credentials against other systems if credentials have
  been reused

## Root Cause

Sensitive authentication information was placed within client-side code.

Any JavaScript, HTML or other resource delivered to the browser should
be considered accessible to the user.

## Mitigation

Authentication credentials should never be embedded within client-side
JavaScript.

Authentication should be performed securely on the server side.

Applications should also use:

- Secure password hashing
- Server-side authentication controls
- Appropriate secrets management
- Proper access-control mechanisms

## Skills Demonstrated

- Web application security testing
- Firefox Developer Tools
- JavaScript source-code inspection
- Authentication analysis
- Information disclosure identification
- Vulnerability analysis
- Security remediation

## Result

The vulnerability was successfully identified and demonstrated within
the authorised academic laboratory environment.

Challenge secrets, credentials, internal URLs and assessment-specific
information have intentionally been excluded from this public repository.

## Ethical & Academic Context

All security testing documented in this repository was conducted within
an authorised university cybersecurity laboratory.

No external or third-party systems were targeted.
