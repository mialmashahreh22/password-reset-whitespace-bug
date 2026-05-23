# Bug Report: Password Reset Whitespace Bug

## Summary

A password reset flow accepts a password with leading whitespace, but login later rejects or normalizes it differently, locking the user out.

## Vulnerability Type

Authentication / Input Consistency

## Severity

Medium

## Related CWE

CWE-178: Improper Handling of Case Sensitivity or Whitespace

## Steps to Reproduce

1. Open password reset or change password.
2. Set a new password with a leading space.
3. Log out.
4. Try logging in with the same password.
5. Observe login failure.

## Expected Behavior

Password creation and login should handle whitespace consistently, either preserving it exactly or rejecting it clearly at creation time.

## Actual Behavior

The reset flow and login flow appear to normalize or store whitespace differently.

## Impact

- Users can accidentally lock themselves out.
- Support burden increases.
- Authentication behavior becomes unpredictable.

## Remediation

- Apply the same normalization rules in password creation and login.
- Prefer clear validation that rejects leading/trailing whitespace with a helpful error.
- Add tests for whitespace edge cases.

## Evidence Guidance

For a real responsible disclosure report, include only authorized evidence:

- Redacted screenshots
- Redacted request and response examples
- Timeline of testing
- Clear reproduction steps
- No real secrets, tokens, private personal data, or destructive live actions

## CTF Lab

The lab in `labs/ctf-game` teaches this bug class using safe mock data. Complete all missions to reveal the flag.
