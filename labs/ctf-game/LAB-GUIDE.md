# Password Reset Whitespace Bug - CTF Lab Guide

This lab is a realistic mock simulation for one bug class.

## Goal

Find the bug in the mock app and unlock the flag.

## How to Run

From this repo root:

```bash
python -m http.server 8000
```

Open:

```text
http://localhost:8000/labs/ctf-game/
```

## What to Do

1. Set the password to the provided value with a leading space.
2. Try logging in with the same value.
3. The login fails even though the reset succeeded.
4. The flag appears when the lockout behavior is reproduced.

## What You Should Learn

Small input-handling differences can break authentication and create serious user-impact bugs.

## Safety

This is a local mock app. Do not repeat these actions against real websites unless you have explicit authorization.
