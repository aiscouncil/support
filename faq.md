# Frequently Asked Questions

Everything you need to know about AI Supreme Council.

## Table of Contents

- [General](#general)
- [Privacy & Security](#privacy--security)
- [Features](#features)
- [Pricing](#pricing)
- [Technical](#technical)

---

## General

### What is AI Supreme Council?

AI Supreme Council is a browser-based platform that lets you chat with multiple AI models (Claude, GPT, Grok, Gemini, and 300+ others) from a single interface. In Council mode, multiple models debate your question through a three-phase deliberation process — fan-out, peer review, and synthesis — to deliver a cross-checked consensus answer.

### Is it really free?

Yes. The free tier gives you access to free models from OpenRouter and Google Gemini with no credit card required. You can also bring your own API keys (BYOK) to use any model on the free plan. The optional Lite subscription ($3-9/month) adds premium features.

### What AI models are supported?

Claude (Anthropic), GPT and o-series (OpenAI), Grok (xAI), Gemini (Google), 300+ models via OpenRouter, and any model you run locally with Ollama. The platform is extensible — new providers can be registered programmatically.

### Where can I access the platform?

Visit [https://aiscouncil.com](https://aiscouncil.com) to use the web app. No download or installation required — it runs entirely in your browser.

---

## Privacy & Security

### Do you store my conversations?

No. All conversations are stored locally in your browser's IndexedDB. There is no backend server processing or storing your chats. Your messages go directly from your browser to each AI provider's API. We never see, intercept, or store your conversations.

### How is my data protected?

AI Supreme Council uses a zero-server architecture. There is no backend server, no database, and no application server to breach. Your data stays in your browser. API keys never leave your device except to go directly to AI provider. All connections use HTTPS/TLS encryption. Bot sharing URLs use URL fragment (after #), which browsers never send to servers.

### What happens to my data if I clear my browser?

Clearing your browser data will permanently delete all conversations, bot configurations, and settings stored locally. We recommend exporting your conversations before clearing browser data. You can export chats from the conversation menu.

### Can anyone see my shared bot URLs?

When you share a bot configuration via URL, the configuration (name, model, system prompt, temperature) is encoded into the URL fragment using Base80 compression. The URL fragment is the part after the # symbol, which browsers never send to servers. This means your configuration is safe, but anyone with the URL can recreate your bot (they need their own API key). Do not share URLs containing sensitive prompts.

### Can I use AI Supreme Council anonymously?

Yes. Guest mode is available without creating an account. Your data is still stored locally in your browser. For full features like bot sharing and cloud sync, create an account with your preferred identity provider.

---

## Features

### What is BYOK (Bring Your Own Key)?

BYOK means you use your own API keys from providers like Anthropic, OpenAI, xAI, Google, or OpenRouter. Your keys are stored in your browser's localStorage and sent directly to provider — we never see or store them. You pay each provider directly at their rates.

### How does Council mode work?

Council mode runs a three-phase deliberation:

1. **Fan-out** — Your question is sent to multiple models in parallel and each produces an independent response
2. **Peer review** — Each model reviews other models' answers, identifying agreements, errors, and missing perspectives
3. **Synthesis** — A chairman model produces a final consensus answer noting where models agreed and diverged

This process helps identify hallucinations, biases, and blind spots by having models cross-check each other's work.

### How does bot sharing work?

Bot configurations (name, model, system prompt, temperature) are encoded into URL fragment using Base80 compression. The URL fragment is the part after the # symbol, which browsers never send to servers. When someone opens a shared URL, they get your exact bot configuration — they just need to add their own API key.

### Can I use local AI models?

Yes. AI Supreme Council supports Ollama for running local LLMs on your own hardware. No API key is required. Ollama models are auto-detected when running locally, and you can configure a custom endpoint in Settings. This gives you complete privacy since no data leaves your machine.

### What can I customize in a bot?

You can configure:

- Bot name and icon
- AI model selection
- System prompt (instructions for the AI)
- Temperature (creativity level)
- Maximum response length
- Council mode settings (number of models, rounds)

---

## Pricing

### How does geo-tiered pricing work?

The Lite subscription price ranges from $3 to $9 per month (USD equivalent) based on your country's cost of living. Your pricing tier is determined automatically via Cloudflare's country detection at the time of subscription. This ensures fair pricing worldwide. Payments are processed by Stripe and PayPal.

**Tier examples:**

- Tier 1 (US, EU, Japan, Australia): $9/month
- Tier 2 (UK, Israel, UAE): $6/month
- Tier 3 (Brazil, Mexico, Turkey): $4/month
- Tier 4 (India, Indonesia, Philippines): $3/month

### What's included in the free tier?

- 20+ free models (OpenRouter + Google Gemini)
- Unlimited conversations
- BYOK for any provider
- Full browser-side privacy
- Bot sharing via URL
- Dark and light themes
- Export chat (JSON / Markdown / Text)
- Local AI via Ollama
- Community plugins

### What's included in the Lite subscription?

Everything in Free, plus:

- 60+ premium models (Claude, GPT, Grok, Gemini)
- Council mode (multi-model deliberation)
- Custom bot personas
- Conversation search
- Usage analytics dashboard
- No ads
- 7-day free trial

### Can I cancel anytime?

Yes. You can cancel your subscription at any time. Access continues until the end of your current billing period. Subscription fees are non-refundable except as required by applicable law.

### Do you offer refunds?

Subscription fees are non-refundable except as required by applicable law. If you believe you're eligible for a refund due to a billing error or service issue, contact us through the [support form](https://docs.google.com/forms/d/e/1FAIpQLSeWfFylvhlamB1IhZ-k-ziM2ggP9WLrzVdjNgexordgNl2CQg/viewform?embedded=true).

---

## Technical

### What browsers are supported?

All modern browsers that support IndexedDB, localStorage, ES6+ JavaScript, and CSS Grid/Flexbox. Recommended: Chrome, Firefox, Safari, Edge (latest versions).

### Does it work offline?

With cached files, the application interface works offline. However, AI model requests require an internet connection (unless using local Ollama models). Your conversations remain accessible offline since they're stored locally.

### How do I export my conversations?

1. Open any conversation
2. Click the "Export" button
3. Choose format: JSON (full backup), Markdown, or Text
4. Save the file to your device

### How do I import conversations?

1. Go to Settings
2. Click "Import"
3. Select your JSON backup file
4. Conversations will be restored to your browser storage

### My API key isn't working. What should I do?

1. Verify the key is copied correctly from your provider's dashboard
2. Ensure the key has the required permissions (some providers distinguish between account keys and API keys)
3. Check that the key hasn't been revoked or expired
4. Try generating a new key from the provider's console
5. Contact us if issues persist

### I'm seeing errors in Council mode

Common causes:

- Not enough API credits on one or more providers
- API key permissions are insufficient
- Network connectivity issues
- Rate limits from providers

Troubleshoot by:

1. Testing each model individually first
2. Checking API key status in provider dashboards
3. Reducing council size (fewer models) to isolate the issue

---

## Still Have Questions?

- Check our [Contact Form](https://docs.google.com/forms/d/e/1FAIpQLSeWfFylvhlamB1IhZ-k-ziM2ggP9WLrzVdjNgexordgNl2CQg/viewform?embedded=true)
- Review [Security documentation](./security.md)
- Read our [Acceptable Use Policy](./acceptable-use.md)
- Visit [aiscouncil.com](https://aiscouncil.com) for live support resources

Last updated: February 2026
