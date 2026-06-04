# JWT Security
## Vulnerability Overview
JSON Web Tokens (JWTs) are commonly used for authentication and authorization.

## Investigation Approach
- Examined JWT structure
- Analysed token contents
- Investigated signature validation behaviour

## Security Impact
Improper JWT validation can lead to authentication bypass.

## Mitigation
- Strong signing algorithms
- Signature verification
- Token expiration enforcement
