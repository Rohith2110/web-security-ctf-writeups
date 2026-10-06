# JWT Authentication and Authorization Weakness

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate how the application used JSON Web Tokens
(JWTs) for authentication and authorization and determine whether the
server securely validated token integrity.

## Vulnerability Identified

The application accepted a modified JWT without properly enforcing
cryptographic signature validation.

The token's signing algorithm could be changed to `none`, allowing token
claims to be modified without a valid signature.

This created an authentication and authorization weakness because the
server trusted manipulated claims contained within an unsigned token.

## Investigation

I authenticated to the application using a standard low-privilege account
and inspected the JWT issued by the server.

The token contained claims representing information such as the user's
identity and role.

I analysed the JWT structure and investigated how the server validated the
token.

During testing, I found that the application accepted a token using the
`none` algorithm.

I modified the identity and role claims within the token and removed the
cryptographic signature.

The server accepted the modified token, demonstrating that insufficient JWT
validation could allow privilege manipulation.

The exact token, account details, internal URLs and challenge secret have
intentionally been excluded from this public write-up.

## Security Impact

Improper JWT validation can potentially allow an attacker to:

- Forge authentication tokens
- Modify identity claims
- Manipulate user roles
- Escalate privileges
- Bypass authorization controls
- Access protected application functionality

The severity can be significant because JWTs are commonly used to represent
authenticated identities and authorization information.

## Root Cause

The server failed to strictly enforce an approved cryptographic signing
algorithm when validating JWTs.

Security-sensitive token properties were therefore trusted without
sufficient verification of the token's authenticity and integrity.

## Mitigation

Applications using JWTs should:

- Explicitly allow only approved signing algorithms
- Reject unsigned tokens
- Verify the token signature before trusting any claims
- Validate issuer and audience values where applicable
- Validate token expiration
- Avoid trusting client-controlled role information without authorization
  checks
- Protect signing keys using appropriate secrets-management practices
- Perform server-side authorization for protected resources

## Detection Opportunities

From a defensive security perspective, suspicious JWT activity may produce
indicators such as:

- Unexpected JWT algorithms
- Unsigned tokens
- Sudden changes in user-role claims
- Low-privilege accounts accessing privileged resources
- Abnormal authentication sequences
- Repeated invalid-token requests
- Privileged actions without corresponding authentication events

Authentication and application logs can be forwarded to a SIEM such as
Splunk or Microsoft Sentinel.

Detection rules could correlate authentication events, token-validation
failures and privileged-resource access to identify suspicious activity.

## Skills Demonstrated

- JSON Web Token analysis
- Authentication security
- Authorization testing
- Token integrity analysis
- Privilege-escalation concepts
- Web application security testing
- Secure authentication design
- Security monitoring concepts
- SIEM-oriented detection thinking

## Result

The JWT validation weakness was successfully identified and demonstrated
within the authorised academic laboratory environment.

Challenge secrets, JWT values, internal URLs, account details and
assessment-specific information have intentionally been excluded from this
public repository.

## Ethical & Academic Context

All testing documented here was conducted within an authorised university
cybersecurity laboratory.

No external or third-party systems were targeted.
