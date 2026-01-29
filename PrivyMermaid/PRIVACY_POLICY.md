# Privacy Policy for PrivyMermaid

**Last Updated:** January 2026

## Overview

PrivyMermaid ("the Extension") is a local-first Mermaid diagram editor. This Privacy Policy explains how we handle information when you use our Chrome extension.

## Our Privacy Commitment

**PrivyMermaid does not collect, store, or transmit any personal data to external servers.** The extension is designed to keep all your data on your device.

## Data Collection

### What We DO NOT Collect

- ❌ Personal information (name, email, address)
- ❌ Usage analytics or telemetry
- ❌ Browsing history
- ❌ Diagram content or prompts sent to our servers (we have no servers)
- ❌ Any data transmitted to external servers

### What Is Stored Locally

The following data is stored **locally on your device only** using Chrome’s storage API:

| Data Type | Purpose | Storage Location |
|-----------|---------|------------------|
| Diagram list | Your saved diagrams (name, source, timestamps) | chrome.storage.local |
| Settings | Ollama endpoint URL, model, temperature, theme | chrome.storage.local |
| Prompt templates | Your custom Fix/Refactor prompts | chrome.storage.local |
| Active diagram ID | Which diagram is currently open | chrome.storage.local |

**This data never leaves your device** and is only accessible by the extension.

## Extension Permissions

The extension requests only the following:

- **storage** — Used to save your diagram list, settings, prompt templates, and active diagram ID locally. All of this stays on your device.
- **contextMenus** — Used to add right-click menu items (“Open in PrivyMermaid”, “Render selection in PrivyMermaid”). If you use “Render selection”, the selected text is passed only to the extension’s own page to open as a new diagram; it is not sent to any server.
- **Host access (localhost / 127.0.0.1)** — Used only to connect to your local Ollama instance for the optional “Ask” and “Fix Diagram” / “Refactor” features. No other network access is requested or used.

## Network Communications

PrivyMermaid only makes network requests in the following scenario:

### Local AI (Ollama) — Optional

- **Destination:** Your local machine (http://localhost or http://127.0.0.1), typically port 11434
- **Purpose:** Send prompts to your locally-running Ollama instance for "Ask" and "Fix Diagram" / "Refactor"
- **Data:** Diagram source, error messages (if any), and your prompts
- **Note:** All AI processing happens on YOUR machine. No data is sent to the internet.

The extension does **not** connect to any other external servers. Diagram rendering uses a bundled Mermaid library (offline); no CDN is required.

## Third-Party Software

- **Mermaid:** The extension includes a local copy of Mermaid (MIT License) for rendering diagrams. No data is sent to Mermaid or any third party for rendering.
- **Ollama:** Optional; you install and run Ollama on your own machine. The extension only talks to your local Ollama instance.

## Data Security

- All stored data uses Chrome’s built-in storage, which is sandboxed to the extension.
- No telemetry, no analytics, no tracking.

## Changes to This Policy

We may update this Privacy Policy from time to time. The "Last Updated" date at the top will be revised when changes are made.

## Contact

For privacy-related questions, please use the Chrome Web Store support page for the extension.
