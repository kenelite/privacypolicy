# Privacy Policy — PrivyMermaid (macOS)

**Last updated:** January 2026

This Privacy Policy describes how PrivyMermaid (“the App”) handles information when you use the macOS application. The App is designed with privacy in mind: we do not collect, transmit, or sell your personal data.

---

## 1. Summary

- **No personal data collection.** We do not collect, store, or transmit any personally identifiable information.
- **No analytics or tracking.** The App does not include analytics, advertising, or third-party tracking.
- **Data stays on your Mac.** All content and settings are stored only on your device.
- **Optional network use.** The App may connect to a local or user-configured Ollama server; no data is sent to our servers or other third parties.

---

## 2. Data Stored on Your Device

The App stores the following data **only on your Mac**, in the standard macOS Application Support folder:

- **Diagrams:** Your Mermaid diagrams and diagram metadata (e.g. titles), saved in a local file (`diagrams.json`).
- **Settings:** App preferences (e.g. Ollama endpoint, Mermaid theme), saved in a local file (`settings.json`).
- **Prompts:** Your editable prompt templates for Generate, Fix, and Refactor, saved in a local file (`prompts.json`).

This data is **never** uploaded to our servers or shared with third parties. It remains under your control and is removed when you delete the App or its Application Support data.

---

## 3. File Access

The App can read and write files **only when you explicitly choose them** (e.g. Import/Export). It uses macOS sandbox “user-selected file” access. We do not access your files without your action.

---

## 4. Network Use

The App may connect to the **internet or your local network** only in the following case:

- **Ollama:** If you enable and configure the Ollama integration, the App sends diagram text and prompts to the Ollama endpoint you specify (by default, `http://localhost:11434`). This communication is between your Mac and your own Ollama instance (or another endpoint you control). We do not receive, store, or process this data.

The App does **not**:

- Phone home to our servers.
- Send analytics, crash reports, or usage data to us or to third parties.
- Include advertising or tracking SDKs.

---

## 5. No Account or Cloud Sync

The App does not require an account. There is no cloud sync, no login, and no server-side storage of your content.

---

## 6. Your Control and Data Deletion

- All App data is stored locally. To delete it, remove the App and, if you wish, delete the folder `~/Library/Application Support/PrivyMermaidMac/`.
- We do not retain copies of your data because we never receive it.

---

## 7. Children’s Privacy

The App does not collect personal information. We do not knowingly collect data from children; the App is not directed at children and does not require age verification.

---

## 8. Changes to This Policy

We may update this Privacy Policy from time to time. The “Last updated” date at the top will be revised when changes are made. Continued use of the App after changes constitutes acceptance of the updated policy. For significant changes, we will provide notice (e.g. in the App or on the App’s web page) where feasible.

---

## 9. Third-Party Software

The App may bundle or use third-party software (e.g. for diagram rendering). Licenses and attribution for such software are set out in **[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)**. That document does not change how we handle your data; this Privacy Policy still applies to the App.

---

## 10. Contact

If you have questions about this Privacy Policy or the App’s handling of data, please contact us at the support or contact address provided in the App Store listing or on the App’s official website.

---

*PrivyMermaid is a macOS application for editing and previewing Mermaid diagrams, with optional local AI assistance via Ollama. This policy applies to the macOS App Store and direct distribution of the App.*
