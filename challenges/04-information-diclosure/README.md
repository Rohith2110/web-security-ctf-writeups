# Information Disclosure Through Exposed Static Resources

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate whether publicly accessible application
resources exposed information that could reveal sensitive or unintended
content.

## Vulnerability Identified

The application exposed sensitive information through publicly accessible
static resources.

By analysing the structure of a legitimate static-resource URL, it was
possible to identify another accessible resource that disclosed information
about a protected location within the application.

## Investigation

I inspected a publicly accessible image used by the web application and
examined its URL structure.

The resource was stored within a predictable static-content directory.

I investigated whether other files could be accessed from the same
location and discovered an exposed text resource.

The information contained within that resource revealed the location of
additional application content.

This demonstrated how publicly accessible files and predictable resource
locations can unintentionally disclose sensitive application information.

The internal paths and challenge secret have intentionally been excluded
from this public write-up.

## Security Impact

Information disclosure vulnerabilities can provide attackers with useful
information about an application's structure.

Depending on the exposed information, this could reveal:

- Internal application paths
- Sensitive configuration information
- Hidden application resources
- Development or debugging files
- Information useful for further attacks

Although information disclosure may appear less severe than direct code
execution, exposed information can assist attackers in identifying and
exploiting additional weaknesses.

## Root Cause

Sensitive information was stored within a location accessible through the
web application.

The application relied on obscurity rather than appropriate access controls
to protect the resource.

## Mitigation

Applications should:

- Avoid storing sensitive files in publicly accessible directories
- Apply appropriate server-side access controls
- Remove unnecessary development and debugging files before deployment
- Review static-resource directories for unintended content
- Avoid relying on unpredictable or hidden URLs as a security control
- Follow least-exposure principles when publishing application resources

## Detection Opportunities

From a defensive perspective, attempts to discover exposed resources may
produce indicators such as:

- Requests for unusual files within static directories
- Repeated requests for different filenames or extensions
- Increased numbers of HTTP 404 responses from a single source
- Requests for configuration, backup or text files
- Sequential resource-enumeration behaviour

Web-server logs can be analysed or forwarded to a SIEM to identify
potential resource-enumeration activity.

## Skills Demonstrated

- Web application reconnaissance
- Static-resource analysis
- Information disclosure identification
- URL and path analysis
- Security impact assessment
- Defensive security analysis
- Web-server log analysis concepts
- SIEM-oriented detection thinking

## Result

The information disclosure weakness was successfully identified and
demonstrated within the authorised academic laboratory environment.

Challenge secrets, internal URLs and assessment-specific resource paths
have intentionally been excluded from this public repository.

## Ethical & Academic Context

All testing documented here was conducted within an authorised university
cybersecurity laboratory.

No external or third-party systems were targeted.
