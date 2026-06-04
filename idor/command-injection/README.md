# Command Injection
## Vulnerability Overview
Command Injection occurs when an application executes operating system commands using unsanitized user input.

## Investigation Approach
- Analysed input fields
- Observed application responses
- Tested command execution behaviour
- Identified input validation weaknesses

## Security Impact
Attackers may execute unintended operating system commands.

## Mitigation
- Input validation
- Parameterized execution
- Principle of least privilege
