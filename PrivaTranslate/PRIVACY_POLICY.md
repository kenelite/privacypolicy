# Privacy Policy for PrivaTranslate

**Last Updated: January 22, 2026**

## Overview

PrivaTranslate is a privacy-first browser extension designed to translate web pages using a locally-running Large Language Model (LLM) via Ollama. **Your data never leaves your device.**

## Data Collection

### What We DO NOT Collect

PrivaTranslate does **NOT** collect, store, transmit, or share any of the following:

- ❌ Personal information
- ❌ Browsing history
- ❌ Web page content
- ❌ Translation requests or results
- ❌ IP addresses
- ❌ Device identifiers
- ❌ Usage analytics or statistics
- ❌ Cookies or tracking data

### What We Store Locally

PrivaTranslate stores the following data **only on your local device** using Chrome's `storage.sync` API:

- ✅ User preferences (Ollama URL, model name, source/target language)
- ✅ Translation mode setting (overlay, replace, or side-by-side)
- ✅ Connection timeout settings

This data is stored locally and synced across your Chrome browsers if you are signed into Chrome. **This data is never sent to us or any third party.**

## Network Requests

### Local Requests Only

PrivaTranslate makes network requests **exclusively** to:

- `http://127.0.0.1` (localhost)
- `http://localhost`

These requests are sent to your **locally-running Ollama server** to perform translations. No data is ever transmitted to external servers, cloud services, or third parties.

### No External Communications

- ❌ No analytics services (Google Analytics, Mixpanel, etc.)
- ❌ No advertising networks
- ❌ No external APIs or cloud translation services
- ❌ No telemetry or crash reporting services

## Permissions

PrivaTranslate requires certain browser permissions to function. Here's why:

| Permission | Purpose |
|------------|---------|
| `storage` | Save your preferences locally |
| `activeTab` | Access current page for translation |
| `scripting` | Extract text and apply translations |
| `contextMenus` | Provide right-click translation option |
| `host_permissions` (localhost) | Communicate with local Ollama server |

## Third-Party Services

PrivaTranslate does not integrate with any third-party services. The only external dependency is **Ollama**, which runs entirely on your local machine.

## Data Security

Since all data processing occurs locally on your device:

- Your translation content never travels over the internet
- There is no server-side storage of your data
- There is no risk of data breaches from our end (we have no servers)

## Children's Privacy

PrivaTranslate does not collect any personal information from anyone, including children under 13 years of age.

## Changes to This Policy

We may update this Privacy Policy from time to time. Any changes will be reflected in the "Last Updated" date at the top of this document.

## Open Source

PrivaTranslate is open source. You can review our code to verify our privacy practices:

- GitHub: [https://github.com/kenelite/PrivaTranslate](https://github.com/kenelite/PrivaTranslate)

## Contact

If you have any questions about this Privacy Policy, please open an issue on our GitHub repository.

---

## Summary

**PrivaTranslate is designed with privacy as the core principle:**

1. 🔒 **Zero data collection** - We collect nothing
2. 🏠 **100% local processing** - All translations happen on your machine
3. 🚫 **No external requests** - Only connects to your local Ollama server
4. 📖 **Open source** - Fully auditable code

**Your privacy is not just a feature—it's our purpose.**
