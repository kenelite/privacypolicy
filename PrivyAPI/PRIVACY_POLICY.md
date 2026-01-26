# Privacy Policy for PrivyAPI

**Last Updated:** January 22, 2025

## Overview

PrivyAPI ("the Extension") is a privacy-first API testing tool designed to keep your data secure and private. This Privacy Policy explains how we handle information when you use our Chrome extension.

## Our Privacy Commitment

**PrivyAPI does not collect, store, or transmit any personal data to external servers.** The extension is designed from the ground up with privacy as a core principle.

## Data Collection

### What We DO NOT Collect

- ❌ Personal information (name, email, address)
- ❌ Usage analytics or telemetry
- ❌ Browsing history
- ❌ API request/response content
- ❌ Authentication tokens or credentials
- ❌ Any data transmitted to our servers (we have no servers)

### What Is Stored Locally

The following data is stored **locally on your device only** using browser's IndexedDB:

| Data Type | Purpose | Storage Location |
|-----------|---------|------------------|
| User Settings | Ollama URL, model preferences | Local (IndexedDB) |
| API Projects | Imported OpenAPI/Swagger specs | Local (IndexedDB) |
| Environment Variables | User-defined variables (baseUrl, etc.) | Local (IndexedDB) |
| Selected States | Currently selected project/endpoint | Local (IndexedDB) |

**This data never leaves your device** and is only accessible by the extension.

## Network Communications

PrivyAPI only makes network requests in the following scenarios:

### 1. Local AI Processing (Ollama)
- **Destination:** Your local machine (127.0.0.1 or localhost)
- **Purpose:** Send prompts to your locally-running Ollama instance
- **Data:** API schema information and user intent (with sensitive data redacted)
- **Note:** All AI processing happens on YOUR machine, not external servers

### 2. API Testing (User-Initiated)
- **Destination:** URLs explicitly specified by you
- **Purpose:** Test API endpoints you choose to test
- **Data:** Request data you create or approve
- **Note:** Only triggered by your explicit action (clicking "Send")

### 3. OpenAPI Import (Optional)
- **Destination:** URLs you provide for importing API specifications
- **Purpose:** Fetch OpenAPI/Swagger JSON files
- **Note:** Only triggered when you explicitly enter a URL and click "Fetch"

## Data Security

### Sensitive Data Redaction
Before sending any data to the local AI (Ollama), the extension automatically redacts potentially sensitive information including:
- Authorization headers
- Passwords and secrets
- API keys
- Tokens
- Email addresses
- Phone numbers

### Local Storage Security
All locally stored data uses browser's built-in IndexedDB, which is:
- Sandboxed to the extension
- Not accessible by websites or other extensions
- Encrypted at rest by the operating system (on supported systems)

## Third-Party Services

PrivyAPI does not integrate with any third-party analytics, advertising, or tracking services.

The only external software PrivyAPI interacts with is:
- **Ollama** - A local LLM server that YOU install and run on YOUR machine

## Data Retention

- **Local Data:** Stored until you uninstall the extension or manually clear it
- **Remote Data:** None (we don't collect any)

To delete all locally stored data:
1. Right-click the PrivyAPI extension icon
2. Select "Remove from Chrome"
3. Confirm removal

Or clear extension data via Chrome settings:
1. Go to `chrome://settings/content/all`
2. Find PrivyAPI
3. Click "Clear data"

## Children's Privacy

PrivyAPI is a developer tool not directed at children under 13. We do not knowingly collect information from children.

## Changes to This Policy

We may update this Privacy Policy from time to time. Changes will be reflected in the "Last Updated" date above. Continued use of the extension after changes constitutes acceptance of the new policy.

## Contact

If you have questions about this Privacy Policy, please contact us at:
- **Email:** [kenelite.sg@gmail.com]

---

## Summary

| Question | Answer |
|----------|--------|
| Do you collect personal data? | **No** |
| Do you use analytics? | **No** |
| Do you share data with third parties? | **No** |
| Where is data stored? | **Locally on your device only** |
| Do you have servers? | **No** |

**PrivyAPI is built for developers who value privacy. Your data stays on your machine.**
