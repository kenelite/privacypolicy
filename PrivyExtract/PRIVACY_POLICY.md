# Privacy Policy for PrivyExtract

**Last Updated:** January 26, 2026

## Overview

PrivyExtract ("we", "our", or "the extension") is committed to protecting your privacy. This Privacy Policy explains how PrivyExtract handles data and what information is collected, used, or shared.

## Core Privacy Principle

**PrivyExtract operates entirely locally on your device. No data is collected, transmitted, or stored by the extension or its developers.**

## Data Collection

### What We Do NOT Collect

PrivyExtract does **NOT** collect, transmit, or store:
- Web page content
- Selected text
- Summaries or generated content
- Browsing history
- Personal information
- Usage statistics
- Device information
- Location data
- Any other user data

### What We Store Locally

PrivyExtract only stores the following information **locally on your device** using Chrome's local storage:
- **Ollama URL**: The address of your local Ollama service (default: http://127.0.0.1:11434)
- **Model Name**: The name of the AI model you prefer to use (e.g., "qwen2.5:7b")
- **Summary Preferences**: Your preferred summary type and length settings

This information is stored only on your device and is never transmitted anywhere.

## How PrivyExtract Works

1. **Content Extraction**: When you request a summary, PrivyExtract extracts text from the current web page or your selected text. This extraction happens entirely in your browser.

2. **Local Processing**: The extracted content is sent **only** to your local Ollama service running on your machine (typically at http://127.0.0.1:11434 or http://localhost:11434).

3. **No External Transmission**: All communication is between your browser and your local Ollama instance. No data is sent to external servers, cloud services, or third parties.

4. **Display**: The generated summary is displayed in the extension's side panel. The summary content is not stored or transmitted.

## Third-Party Services

PrivyExtract does not use any third-party analytics, tracking, or data collection services. The extension only communicates with:
- Your local Ollama service (running on your machine)
- Chrome's built-in storage API (for local settings only)

## Data Sharing

**We do not share, sell, or transmit any data to any party.** All processing happens locally on your device.

## User Control

You have complete control over:
- What content to summarize
- Which AI model to use
- Your Ollama configuration
- All locally stored settings

You can clear all stored settings at any time by:
1. Opening Chrome's extension settings
2. Finding PrivyExtract
3. Clicking "Remove" or clearing extension data

## Children's Privacy

PrivyExtract does not knowingly collect any information from children. Since we collect no data, this is not applicable.

## Changes to This Privacy Policy

We may update this Privacy Policy from time to time. Any changes will be posted on this page with an updated "Last Updated" date. We encourage you to review this Privacy Policy periodically.

## Contact

If you have any questions about this Privacy Policy, please contact us through the extension's GitHub repository or issue tracker.

## Compliance

This Privacy Policy complies with:
- General Data Protection Regulation (GDPR)
- California Consumer Privacy Act (CCPA)
- Chrome Web Store Privacy Requirements

---

**Summary**: PrivyExtract collects zero data, transmits zero data, and stores only your local configuration preferences on your device. Your privacy is our top priority.
