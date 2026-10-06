# OS Command Injection

## Overview

This exercise was completed in an authorised university web security
laboratory as part of my MSc Cybersecurity and Machine Learning studies.

The objective was to investigate how the application handled user-supplied
input and determine whether that input could influence operating-system
commands executed by the server.

## Vulnerability Identified

The application passed user-controlled input to a system command without
sufficient validation or sanitisation.

This created an OS command injection vulnerability, where specially
crafted input could cause the server to execute additional commands.

## Investigation

I examined an application input field that accepted an identifier.

During testing, I observed behaviour indicating that the supplied value
was being incorporated into a system command on the server.

I then tested whether command syntax could alter the intended execution
flow.

The application executed an additional command supplied through the input,
confirming the presence of an OS command injection vulnerability.

The exact challenge payload and secret have been intentionally excluded
from this public write-up.

## Security Impact

Successful command injection can have serious consequences, including:

- Execution of unauthorised operating-system commands
- Exposure of sensitive files or application data
- Modification or deletion of server-side information
- Compromise of the application server
- Potential movement to other systems if additional weaknesses exist

The actual impact depends on the privileges assigned to the vulnerable
application process.

## Root Cause

User-controlled input was incorporated into an operating-system command
without adequate validation or separation between data and command syntax.

Applications should avoid constructing shell commands directly from
untrusted input.

## Mitigation

Applications should:

- Avoid invoking operating-system commands when safer APIs are available
- Never directly concatenate user input into shell commands
- Apply strict allow-list input validation
- Use parameterised or structured APIs where possible
- Run application services with least privilege
- Monitor application and system logs for suspicious command-execution behaviour

## Detection Opportunities

From a defensive security perspective, command injection attempts may
produce observable indicators such as:

- Unusual characters or command syntax within HTTP parameters
- Unexpected processes spawned by a web application
- Web-server processes launching command interpreters or system utilities
- Requests followed by unusual file-access activity
- Repeated malformed or suspicious application requests

These indicators could potentially be correlated within a SIEM to identify
command-injection attempts.

## Skills Demonstrated

- Web application security testing
- Input validation testing
- OS command injection analysis
- Server-side vulnerability analysis
- Security impact assessment
- Secure coding recommendations
- Defensive detection thinking
- SIEM-oriented security analysis

## Result

The vulnerability was successfully identified and demonstrated within the
authorised academic laboratory environment.

Challenge secrets, internal URLs and assessment-specific payloads have
intentionally been excluded from this public repository.

## Ethical & Academic Context

All testing documented here was conducted within an authorised university
cybersecurity laboratory.

No external or third-party systems were targeted.
