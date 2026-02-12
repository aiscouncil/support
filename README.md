# AI Supreme Council Support

Welcome to the official support repository for AI Supreme Council. This repository contains comprehensive support documentation, FAQs, and resources to help you get the most out of the platform.

## Quick Links

- **[📋 Frequently Asked Questions](./faq.md)** - Common questions and answers
- **[🔒 Security & Vulnerability Reporting](./security.md)** - Security practices and bug bounty
- **[📜 Acceptable Use Policy](./acceptable-use.md)** - What is and isn't permitted
- **[❓ Get Help](./CONTACT.md)** - How to contact us for support

## Getting Started

**What is AI Supreme Council?**

AI Supreme Council is a browser-based platform that lets you chat with multiple AI models (Claude, GPT, Grok, Gemini, and 300+ others) from a single interface. In Council mode, multiple models debate your question through a three-phase deliberation process to deliver a cross-checked consensus answer.

**Core Features:**

- ✅ **Zero-server architecture** - Your conversations and API keys never leave your browser
- ✅ **Council mode** - Multiple AI models debate and reach consensus
- ✅ **BYOK** - Bring Your Own API keys from any provider
- ✅ **Local AI** - Run models locally via Ollama
- ✅ **Bot sharing** - Share configurations via URL (no data leaves your device)
- ✅ **Free to start** - No credit card required for free tier

## Platform

- 🌐 **Web App:** [https://aiscouncil.com](https://aiscouncil.com)
- 📰 **Blog/News:** [https://www.aiscouncil.com/news](https://www.aiscouncil.com/news)
- 📖 **Marketing Site:** [https://www.aiscouncil.com](https://www.aiscouncil.com)

## Supported AI Providers

| Provider   | Models                               | Notes                 |
| ---------- | ------------------------------------ | --------------------- |
| Anthropic  | Claude, Claude 3 Opus, Sonnet, Haiku | Premium provider      |
| OpenAI     | GPT-4, GPT-4o, o1, o1-mini, o3-mini  | Premium provider      |
| xAI        | Grok, Grok-2                         | Premium provider      |
| Google     | Gemini, Gemini Pro, Gemini Flash     | Premium provider      |
| OpenRouter | 300+ models from 50+ providers       | Free & premium models |
| Ollama     | Local models (Llama, Mistral, etc.)  | Runs on your hardware |

> **Note:** Your use of AI providers is governed by their terms. Please check each provider's website directly for their latest terms and privacy policies, as we do not maintain or guarantee accuracy of third-party policy information.

## Pricing

### Free Tier

- ✅ 20+ free models (OpenRouter + Google Gemini)
- ✅ Unlimited conversations
- ✅ BYOK for any provider
- ✅ Full browser-side privacy
- ✅ Bot sharing via URL
- ✅ Dark and light themes
- ✅ Export chat (JSON / Markdown / Text)
- ✅ Local AI via Ollama
- ✅ Community plugins

### Lite Subscription

- 💰 $3–9/month (geo-tiered based on your country)
- ✅ Everything in Free
- ✅ 60+ premium models (Claude, GPT, Grok, Gemini)
- ✅ Council mode (multi-model deliberation)
- ✅ Custom bot personas
- ✅ Conversation search
- ✅ Usage analytics dashboard
- ✅ No ads
- ✅ 7-day free trial

**Yearly savings:** Save up to 50% when you choose annual billing.

## Authentication Options

- Google Sign-In
- Sign in with Apple
- GitHub OAuth
- Facebook Login
- WeChat OAuth
- Guest mode (no account required)

## Privacy & Security

AI Supreme Council uses a **zero-server architecture**:

- 🚫 No backend server processing your conversations
- 🚫 No database storing your chats
- 🔒 All data stored locally in your browser (IndexedDB + localStorage)
- 🔐 API keys sent directly to providers (we never see them)
- 🔒 All connections use HTTPS/TLS encryption
- 🔗 Shared URLs use URL fragments (never sent to servers)

For detailed security information, see [security.md](./security.md).

## Browser Support

AI Supreme Council works in all modern browsers that support:

- IndexedDB (for conversation storage)
- localStorage (for settings and API keys)
- ES6+ JavaScript
- CSS Grid and Flexbox

Recommended browsers: Chrome, Firefox, Safari, Edge (latest versions)

## Common Issues

**"My bot URL isn't working"**

- Check that the URL is complete (copy from address bar, not shared text)
- Verify your API keys are configured in Settings
- Some browsers may truncate long URLs in chat apps

**"I can't see local Ollama models"**

- Ensure Ollama is running locally: `ollama serve`
- Check that Ollama API is accessible at `http://localhost:11434`
- Try downloading at least one model: `ollama pull llama3`

**"API key authentication failed"**

- Verify the key is correct (copy from provider dashboard)
- Check that the key has appropriate permissions
- Some providers require API keys to be created in their console (not account keys)

**"Council mode isn't working"**

- Council mode requires a Lite subscription
- Ensure at least 2 models are selected for the council
- Check your API keys have sufficient credits/usage limits

## Data Backup

Your data is stored locally in your browser. To back up:

1. Go to a conversation
2. Click "Export" button
3. Choose JSON format
4. Save the file to your computer

To restore from backup, import the JSON file through Settings.

## Getting Help

If you can't find an answer in our documentation:

1. Check the [FAQ](./faq.md) for common questions
2. Review [security.md](./security.md) for security concerns
3. Visit our [Contact Form](https://docs.google.com/forms/d/e/1FAIpQLSeWfFylvhlamB1IhZ-k-ziM2ggP9WLrzVdjNgexordgNl2CQg/viewform?embedded=true)
4. Join our [GitHub Discussions](https://github.com/aiscouncil/support/discussions)

---

**Operator:** BizTransit Sdn Bhd  
**Platform:** https://aiscouncil.com  
**Repository:** https://github.com/aiscouncil/support

Last updated: February 2026
