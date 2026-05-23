# Remediation Notes

## Main Fixes

- Apply the same normalization rules in password creation and login.
- Prefer clear validation that rejects leading/trailing whitespace with a helpful error.
- Add tests for whitespace edge cases.

## Engineering Checklist

- Add server-side authorization checks.
- Add regression tests for the reported scenario.
- Log suspicious repeated attempts.
- Return minimal response data.
- Document intended business rules.
- Review related endpoints for the same pattern.

## Verification

After remediation, confirm:

- The old step no longer reproduces: Open password reset or change password.
- The old step no longer reproduces: Set a new password with a leading space.
- The old step no longer reproduces: Log out.
- The old step no longer reproduces: Try logging in with the same password.
- The old step no longer reproduces: Observe login failure.
