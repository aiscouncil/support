# Security & Vulnerability Reporting

Security is fundamental to AI Supreme Council. Our zero-server architecture is designed to protect your privacy by default.

## Zero-Server Architecture

AI Supreme Council is designed with a fundamentally different security model than traditional SaaS applications. There is no backend server processing your conversations.

### What This Means:

- **No conversation relay:** Your messages are sent directly from your browser to each AI provider's API (Anthropic, OpenAI, xAI, Google, etc.). Our servers never see, process, or store the content of your conversations.

- **No server-side storage:** We do not operate databases containing user conversations, bot configurations, or chat histories. All of this lives in your browser.

- **Static hosting:** Our web application is served as static files from Cloudflare Pages. There is no application server, no API backend, and no database to breach.

## Browser-Side Storage

All user data is stored locally in your browser using standard web storage APIs:

| Storage         | Data                            | Purpose                   |
| --------------- | ------------------------------- | ------------------------- |
| localStorage    | Theme, API keys, user session   | Sync reads at boot        |
| IndexedDB       | Bots, chat histories, addons    | Large data, no size limit |
| OPFS (optional) | WASM modules, large binary data | Concurrent access, SQLite |

**Key points:**

- This data never leaves your device unless you explicitly export it or share a bot via URL
- Clearing your browser data removes all application data permanently
- You are in full control of your data

## API Key Handling

Your API keys are the most sensitive data in the application. Here is how they are handled:

### Storage

API keys are stored in your browser's localStorage under keys like `ais-apikey-anthropic`, `ais-apikey-openai`, etc. They are never sent to our servers.

### Transmission

Keys are sent directly from your browser to the AI provider's API endpoint over HTTPS. The connection is between your browser and provider — we are not in the path.

### URL Safety

API keys are never included in bot sharing URLs. The URL encoding system explicitly excludes keys from the shareable configuration.

### No Logging

We do not log, intercept, or have any mechanism to access your API keys.

### Recommendation

Use provider-specific API keys with minimum required permissions. If you suspect a key has been compromised, revoke it immediately through the provider's dashboard.

## Encryption in Transit

- All connections to aiscouncil.com and bcz.co use HTTPS with TLS 1.2+ encryption
- HSTS (HTTP Strict Transport Security) is enabled to prevent downgrade attacks
- All connections from your browser to AI provider APIs use HTTPS
- URL fragments (the `#` portion used for bot sharing) are never sent to servers by browsers — this is a fundamental property of how URLs work

## Payment Security

We do not handle payment card data directly. All payment processing is delegated to trusted, certified processors:

- **Stripe:** PCI DSS Level 1 compliant. Card numbers and payment details are collected and processed entirely by Stripe's infrastructure.
- **PayPal:** PCI DSS Level 1 compliant. Payment is handled through PayPal's secure payment flow.

We receive only a payment confirmation token and subscription status. We never see, store, or process your credit card number, CVV, or banking details.

## Authentication

We use industry-standard OAuth 2.0 and OpenID Connect (OIDC) protocols for authentication:

| Provider | Protocol                  |
| -------- | ------------------------- |
| Google   | OAuth 2.0 / OIDC          |
| Apple    | Sign in with Apple (OIDC) |
| GitHub   | OAuth 2.0                 |
| Facebook | OAuth 2.0                 |
| WeChat   | OAuth 2.0                 |

### Authentication Security Details:

- **Session tokens:** JWT (JSON Web Tokens) signed with HS256, with a 24-hour expiry
- **No password storage:** We never receive, store, or manage passwords. Authentication is fully delegated to identity providers.
- **Guest mode:** Available for users who prefer not to authenticate. Guest mode provides access to core features without any account data.

## What We Do Not Do

- No analytics services (no Google Analytics, no Mixpanel, no Amplitude)
- No tracking pixels or advertising beacons
- No cross-site tracking cookies
- No fingerprinting or device identification
- No server-side logging of user activity beyond standard Cloudflare CDN access logs
- No data sales or sharing with advertisers

## Vulnerability Reporting

We take security seriously and appreciate responsible disclosure. If you discover a security vulnerability in AI Supreme Council, please report it.

### How to Report

**Email:** [security@aiscouncil.com](mailto:security@aiscouncil.com)

Please include in your report:

- Description of the vulnerability
- Steps to reproduce
- Potential impact assessment
- Any proof-of-concept code or screenshots

### Our Commitment

- ✅ We will acknowledge receipt within 24 hours
- ✅ We will provide an initial assessment within 72 hours
- ✅ We will work with you to understand and resolve the issue
- ✅ We will credit you in our security acknowledgments (unless you prefer to remain anonymous)
- ✅ We will not take legal action against researchers acting in good faith

### Scope

The following are in scope for security reports:

- aiscouncil.com and all subdomains
- bcz.co and all subdomains
- The browser application (index.html, s/index.html)
- The Chrome extension
- Community-maintained code at [github.com/aiscouncil](https://github.com/aiscouncil)

**Out of scope:** Third-party services (Anthropic, OpenAI, xAI, Google, etc.) are out of scope. Please report vulnerabilities in those services directly to the respective provider.

### Exclusions

We do not consider the following as eligible for bug bounties:

- Issues requiring physical access to a user's device
- Issues requiring already compromised credentials
- Issues related to social engineering or phishing
- Spam or DOS attacks on our infrastructure
- Vulnerabilities in third-party services we integrate with

## Security Updates

Since AI Supreme Council is a browser application served from a CDN, security updates are deployed instantly — every page load gets the latest version. There are no update mechanisms to manage, no patches to install, and no version fragmentation.

## Best Practices for Users

### Protect Your Account

- Use strong, unique passwords with your identity providers (Google, Apple, GitHub, etc.)
- Enable two-factor authentication (2FA) on your identity provider accounts
- Don't share your account credentials with others
- Sign out when using shared devices

### Protect Your API Keys

- Never share API keys publicly (GitHub repositories, pastebins, etc.)
- Rotate API keys regularly if you use them frequently
- Use the minimum required permissions for each key
- Revoke compromised keys immediately from provider dashboards
- Different keys for different applications/uses

### Protect Your Conversations

- Be aware that clearing browser data permanently deletes all your conversations
- Export important conversations as backups
- Don't share sensitive information in public bot URLs
- Remember that conversations are stored locally — losing access to your device means losing access to your data

### Browser Security

- Keep your browser updated to the latest version
- Be cautious of browser extensions that may inject scripts
- Don't use the platform on public or shared devices for sensitive conversations
- Clear browser cache and cookies periodically

## Compliance

AI Supreme Council is operated by BizTransit Sdn Bhd, a company registered in Malaysia. We strive to comply with applicable privacy and security regulations globally.

### Data Protection

- We do not collect, process, or store personal data beyond what's necessary for authentication
- Your conversations and API keys remain under your control
- We do not share or sell user data

### Cross-Border Transfers

Since all user data remains on your device and API keys connect directly to providers, cross-border data transfers are governed by your chosen AI providers' policies, not by our infrastructure.

---

## Questions?

For security-related inquiries or to report vulnerabilities:

- Email: [security@aiscouncil.com](mailto:security@aiscouncil.com)
- GitHub: [github.com/aiscouncil/support](https://github.com/aiscouncil/support)

For other support needs, visit our [contact form](https://docs.google.com/forms/d/e/1FAIpQLSeWfFylvhlamB1IhZ-k-ziM2ggP9WLrzVdjNgexordgNl2CQg/viewform?embedded=true).

Last updated: February 2026
