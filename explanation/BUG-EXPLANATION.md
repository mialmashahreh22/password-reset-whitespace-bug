# Password Reset Whitespace Bug - Bug Explanation

## What Is the Bug?

The password reset page accepts a password with a leading space, but the login page handles that same password differently, causing lockout.

## Vulnerability Type

Authentication / Input Consistency

## Why It Happens

One flow preserves the password exactly while another flow trims whitespace before comparing it. Authentication flows must handle the same input consistently.

## Why It Matters

Small input-handling differences can break authentication and create serious user-impact bugs.

## Safe Lab Version

This repository includes a safe local simulation of the bug. The lab does not contact any real target or live service.

Lab path:

```text
labs/ctf-game/
```

## How to Fix

- Use the same password processing rules during reset and login.
- Reject leading/trailing whitespace with a clear warning, or preserve it exactly everywhere.
- Add tests for leading spaces, trailing spaces, tabs, and copied passwords.

## Responsible Disclosure Note

For a real report, keep evidence redacted, avoid publishing secrets or private user data, and test only systems where you have permission.
