# Insecure Direct Object Reference (IDOR)
## Vulnerability Overview
An IDOR vulnerability occurs when applications expose references to internal objects without proper access controls.

## Investigation Approach
- Examined request parameters
- Identified object identifiers
- Tested access controls
- Analysed application responses

## Security Impact
Attackers may gain unauthorized access to information or resources.

## Mitigation
- Implement authorization checks
- Validate user permissions
- Use indirect object references
