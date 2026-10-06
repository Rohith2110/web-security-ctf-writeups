# LSB Steganography Analysis

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate whether an image supplied by the
application contained hidden information.

## Technique Identified

The image contained information hidden using Least Significant Bit (LSB)
steganography.

LSB steganography works by modifying the least significant bits of image
pixel values. Small changes to these bits are usually difficult to notice
visually but can be used to encode hidden information.

## Investigation

I downloaded the image provided by the web application and investigated
whether it contained concealed data.

I used a steganography analysis tool to inspect the least significant bits
of the image's pixel data.

The analysis revealed hidden ASCII information embedded within the image.

The recovered information provided additional information required to
progress through the authorised laboratory exercise.

The hidden value, internal resource path and challenge secret have
intentionally been excluded from this public write-up.

## Security Relevance

Steganography can be used to conceal information inside apparently normal
files such as:

- Images
- Audio files
- Video files
- Documents

From a cybersecurity perspective, steganography may be relevant to:

- Covert data transfer
- Data exfiltration
- Malware communication
- Concealing configuration information
- Digital forensic investigations

## Defensive Considerations

Potential defensive approaches include:

- Analysing suspicious media files
- Comparing file characteristics against expected formats
- Monitoring unusual file transfers
- Using steganalysis tools during forensic investigations
- Correlating suspicious files with endpoint and network activity

Steganography is difficult to detect using network monitoring alone because
the carrier file may appear legitimate.

## Detection Opportunities

In a SOC or incident-response environment, suspicious media files could be
investigated alongside other telemetry such as:

- Unusual file downloads
- Unexpected outbound file transfers
- Endpoint process activity involving image-processing tools
- Files received from suspicious sources
- Abnormal file sizes or metadata
- Threat-intelligence indicators associated with the file source

This demonstrates how file analysis can complement SIEM and endpoint
telemetry during an investigation.

## Skills Demonstrated

- Steganography analysis
- Least Significant Bit concepts
- Hidden-data extraction
- Digital investigation
- File analysis
- Security impact assessment
- Defensive security thinking
- Incident-response analysis

## Result

Hidden information was successfully identified within the image during the
authorised academic laboratory exercise.

Challenge secrets, hidden values, internal URLs and assessment-specific
information have intentionally been excluded from this public repository.

## Ethical & Academic Context

All analysis documented here was conducted within an authorised university
cybersecurity laboratory.

No external or third-party systems were targeted.
