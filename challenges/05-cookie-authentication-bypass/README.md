# Cookie-Based Authentication Bypass

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate how the application used browser cookies
during authentication and determine whether client-controlled cookie values
could influence access to protected functionality.

## Vulnerability Identified

The application relied on a client-controlled cookie when making an
authentication decision.

Because cookies are stored on the client and can be modified by the user,
security-sensitive decisions should not rely solely on untrusted cookie
values.

## Investigation

I interacted with the application's authentication functionality and used
browser developer tools to inspect the cookies stored by the application.

During the investigation, I identified a cookie that appeared to influence
access to protected content.

I modified the client-controlled cookie value and observed that the
application accepted the altered value.

This demonstrated that the authentication mechanism trusted information
controlled by the client without sufficient server-side verification.

The exact cookie value, internal resource path and challenge secret have
intentionally been excluded from this public write-up.

## Security Impact

Trusting client-controlled cookies for authentication or authorization can
potentially allow an attacker to:

- Bypass authentication controls
- Manipulate application state
- Access protected functionality
- Impersonate another privilege level
- Circumvent intended access restrictions

## Root Cause

The application trusted client-side state when making a security-sensitive
authentication decision.

Values received from browser cookies should be considered untrusted input
unless their integrity and authenticity are securely verified.

## Mitigation

Applications should:

- Perform authentication and authorization checks on the server
- Avoid trusting plain client-controlled values for security decisions
- Use secure server-side session management
- Protect session identifiers against tampering
- Use Secure, HttpOnly and appropriate SameSite cookie attributes
- Regenerate session identifiers after authentication
- Validate authorization for every protected request

## Detection Opportunities

From a defensive security perspective, authentication manipulation may
produce indicators such as:

- Unexpected changes in authentication-related cookie values
- Access to protected resources without a normal authentication sequence
- Repeated authentication failures followed by successful privileged access
- Unusual session behaviour
- Sudden privilege changes within the same session

Authentication and application logs can be forwarded to a SIEM and
correlated to identify suspicious session behaviour.

## Skills Demonstrated

- Web application security testing
- Browser cookie analysis
- Authentication testing
- Session-security analysis
- Client-side trust analysis
- Access-control assessment
- Security remediation
- SIEM-oriented detection thinking

## Result

The authentication weakness was successfully identified and demonstrated
within the authorised academic laboratory environment.

Challenge secrets, internal URLs, cookie values and assessment-specific
information have intentionally been excluded from this public repository.

## Ethical & Academic Context

All testing documented here was conducted within an authorised university
cybersecurity laboratory.

No external or third-party systems were targeted.
