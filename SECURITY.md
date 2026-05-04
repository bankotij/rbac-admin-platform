# Security

## Public demo

The [README](README.md) **Live Demo** section lists **intentional weak credentials** (`admin123`, `manager123`, `viewer123`) so visitors can try the app without signing up. These are **not secrets** and exist only in the **throwaway** demo database.

- **Do not** reuse these passwords for any other service.
- **Do not** point a production database or real customer data at the public demo without a full security review and credential rotation.
- If you fork this project, **change** `SECRET_KEY`, database credentials, and all seeded user passwords before deploying.

## Reporting issues

If you find a security vulnerability, please open a private security advisory on GitHub (or contact the maintainer) rather than filing a public issue with exploit details.

## Local & self-hosted use

- Generate a long random `SECRET_KEY` (32+ bytes).
- Use managed PostgreSQL with TLS (`ssl=require` in `DATABASE_URL` where supported).
- Restrict `CORS_ORIGINS` to your real frontend origin(s) in production.
- Prefer **httpOnly** cookies for refresh tokens in a future hardening pass; the current template stores JWTs in `localStorage` for simplicity—understand the XSS tradeoff.

This document is **not** a compliance attestation; it is an honest disclaimer for a portfolio / template repository.
