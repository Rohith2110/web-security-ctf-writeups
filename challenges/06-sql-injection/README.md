# SQL Injection

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate how the application handled user-controlled
input used in database queries and determine whether insufficient input
handling could lead to SQL injection.

## Vulnerability Identified

The application contained an SQL injection vulnerability within a
user-controlled request parameter.

The supplied value was incorporated into a database query without sufficient
protection, allowing the intended SQL query structure to be manipulated.

## Investigation

I analysed a parameter used by the application to retrieve content associated
with a particular author.

During testing, I identified behaviour suggesting that the parameter was
being incorporated directly into an SQL query.

I tested whether SQL syntax could modify the application's database query.

A UNION-based SQL injection demonstrated that additional information could
be retrieved from the application's database beyond what the normal
functionality intended to expose.

The exact payload, usernames, internal paths and challenge secret have
intentionally been excluded from this public write-up.

## Security Impact

Successful SQL injection can potentially allow an attacker to:

- Access sensitive database information
- Bypass application access controls
- Retrieve user or authentication data
- Modify or delete database records
- Manipulate application behaviour
- Compromise the confidentiality and integrity of stored information

The exact impact depends on the privileges assigned to the application's
database account and the database configuration.

## Root Cause

User-controlled input was incorporated into a database query without
sufficient separation between data and SQL instructions.

The application therefore allowed supplied input to influence the structure
of the database query.

## Mitigation

Applications should:

- Use parameterised queries or prepared statements
- Avoid constructing SQL queries through string concatenation
- Validate user-controlled input
- Apply least privilege to database accounts
- Avoid exposing detailed database errors to users
- Perform appropriate server-side authorization checks
- Monitor application and database logs for suspicious query behaviour

## Detection Opportunities

From a defensive security perspective, SQL injection attempts may generate
observable indicators such as:

- Unusual SQL-related syntax within HTTP parameters
- Repeated malformed requests
- Abnormal database errors
- Unexpected query patterns
- Large or unusual database responses
- Repeated attempts against the same application parameter

Web application, database and WAF logs can be forwarded to a SIEM such as
Splunk or Microsoft Sentinel for correlation and alerting.

Detection logic could identify repeated suspicious request patterns and
correlate them with database or application errors.

## Skills Demonstrated

- Web application security testing
- SQL injection analysis
- HTTP parameter analysis
- Database security concepts
- Input validation assessment
- Vulnerability impact analysis
- Secure coding recommendations
- Security monitoring concepts
- SIEM-oriented detection thinking

## Result

The SQL injection vulnerability was successfully identified and demonstrated
within the authorised academic laboratory environment.

Challenge secrets, internal URLs, usernames and assessment-specific payloads
have intentionally been excluded from this public repository.

## Ethical & Academic Context

All testing documented here was conducted within an authorised university
cybersecurity laboratory.

No external or third-party systems were targeted.
