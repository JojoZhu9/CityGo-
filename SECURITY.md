# Security Policy

## Supported Scope

Security reports are welcome for the repository and its Android application. This course project does not provide a production support or release-service commitment.

## Report Privately

Do not open a public issue for a suspected vulnerability or exposed credential. Use the repository's private security-advisory reporting channel when available, or email the monitored project contact at `jiuzhou.zhu@ucdconnect.ie`. Include only the minimum information needed to reproduce the issue.

## Sensitive Information

Report immediately if you find any of the following:

- Exposed Maps SDK for Android keys or Google Maps Platform web-service credentials.
- Maps SDK for Android keys that lack both API restrictions and Android application restrictions for the intended application ID and signing certificate.
- Backend or web-service credentials that lack API restrictions or appropriate server-side restrictions, such as server identity or IP restrictions.
- AI service credentials, including DeepSeek API keys or authorization tokens.
- Credentials in source, issue attachments, logs, APKs, or other generated artifacts.

Remove or redact all secrets from reports, logs, screenshots, and reproduction material. Include affected files or components, a concise impact description, and safe reproduction steps. Maintainers will acknowledge receipt, assess the report, rotate or revoke affected credentials where appropriate, and coordinate a disclosure path privately.

## Credential Restrictions

Use a dedicated Android SDK key for Maps SDK for Android. Restrict it to only the required Android SDK APIs and to the intended Android application ID and signing certificate. Because the key is distributed in the APK, treat it as recoverable even when these restrictions are configured.

Do not embed backend or web-service credentials for Directions, Geocoding, Places Text Search, Nearby Search, DeepSeek, or similar REST APIs in the Android app. Send those requests through a trusted backend, use separate credentials restricted to only the required APIs, and apply server identity or IP restrictions where the provider supports them. Android application restrictions do not protect credentials used for REST web-service calls.
