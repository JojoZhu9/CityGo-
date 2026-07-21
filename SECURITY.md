# Security Policy

## Supported Scope

Security reports are welcome for the repository and its Android application. This course project does not provide a production support or release-service commitment.

## Report Privately

Do not open a public issue for a suspected vulnerability or exposed credential. Use the repository's private security-advisory reporting channel when available. If that channel is unavailable, contact a listed project maintainer privately through their GitHub profile and include only the minimum information needed to reproduce the issue.

## Sensitive Information

Report immediately if you find any of the following:

- Exposed Google Maps, Places, or Directions API keys.
- Google Maps credentials that are unrestricted, enabled for unnecessary APIs, or not limited to the intended Android application ID and signing certificate.
- AI service credentials, including DeepSeek API keys or authorization tokens.
- Credentials in source, issue attachments, logs, APKs, or other generated artifacts.

Remove or redact all secrets from reports, logs, screenshots, and reproduction material. Include affected files or components, a concise impact description, and safe reproduction steps. Maintainers will acknowledge receipt, assess the report, rotate or revoke affected credentials where appropriate, and coordinate a disclosure path privately.
