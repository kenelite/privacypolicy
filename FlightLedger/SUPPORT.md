# FlightLedger — Support

This document covers how to get help, common issues, and troubleshooting for **FlightLedger** (iOS 17+).

---

## Getting help

- **Documentation:** Start with the [README](README.md) for setup, quick start, and project structure.
- **Issues:** For bugs or feature requests, open an issue in the project repository (if applicable).
- **Build / development:** This section and the troubleshooting below cover most build and runtime issues.

---

## Requirements

- **Xcode:** Recent Xcode (14+ recommended; project may reference Xcode 15+).
- **iOS:** 17.0 or later (device or simulator).
- **macOS:** Required for building with Xcode.
- **Optional:** [XcodeGen](https://github.com/yonaskolb/XcodeGen) for generating the Xcode project from `project.yml` (`brew install xcodegen`).

---

## Troubleshooting

### Build & run

**“Please select an available device or choose a simulated device as the destination.”**

- In Xcode, use the **destination** dropdown in the toolbar (next to the Run button) and choose an **iPhone** simulator (e.g. iPhone 16).
- If the list is empty: **Xcode → Settings → Platforms** and download an iOS simulator runtime.

**“No profiles for 'com.flightledger.app' were found”**

- You’re building for a **physical device** but no provisioning profile exists for this app.
- **Fix:** In Xcode, select the **FlightLedger** target → **Signing & Capabilities** → enable **Automatically manage signing** and choose your **Team** (Apple ID). Xcode will create the development profile.
- **Alternative:** Run on the **simulator** only (no provisioning profile needed).

**“Signing for 'FlightLedger' requires a development team.”**

- **Fix:** **FlightLedger** target → **Signing & Capabilities** → set **Team** to your Apple ID (or add an account via **Add an Account…**).

**“The stickers icon set, app icon set, or icon stack named 'AppIcon' did not have any applicable content.”**

- The app icon image must be **1024×1024** and match the size declared in `Resources/Assets.xcassets/AppIcon.appiconset/Contents.json`. If you replaced the icon, ensure the PNG is exactly 1024×1024.

### XcodeGen

**Project doesn’t include Resources / Assets after `xcodegen generate`**

- In `project.yml`, the **Resources** folder must be listed under the target’s **sources** with `buildPhase: resources`. Example:

  ```yaml
  sources:
    - path: Sources
    - path: Resources
      buildPhase: resources
  ```

- Run `xcodegen generate` again and reopen the project.

**Regenerating the Xcode project**

- From the project root: `xcodegen generate`
- Then open: `open FlightLedger.xcodeproj`

### App behavior

**“Airports CSV not found”**

- The app looks for `airports.csv` (OurAirports format) or `airports_sample.csv` inside `Resources/Airports/`. The importer now tries several bundle paths; if it still fails, ensure **Resources** is included in the target’s **Copy Bundle Resources** (e.g. run `xcodegen generate` with `resources` in `project.yml`), then clean build (⇧⌘K) and run again.
- If you see this in the console but the app otherwise works, airport data may not have loaded; add a full dataset (see README: OurAirports **airports.csv** for global coverage including China).

**Console / system messages you can ignore**

These are **system or framework** messages, not bugs in FlightLedger. They often appear in the **Simulator** or under load and can be ignored unless the app actually crashes or misbehaves.

| Message | Meaning |
|--------|--------|
| **MA-auto{_failedLockContent}** / **com.apple.MobileAssetError.AutoAsset:6503** | Apple Mobile Asset (automatic updates for dictionaries, language data). Common in Simulator; harmless. |
| **AddInstanceForFactory: No factory registered for id … F8BB1C28-BAE8-11D6-9C31-00039315CD46** | Audio / Core Media factory (e.g. HAL). Often in Simulator when no real audio device. Harmless. |
| **HALC_ProxyIOContext::IOWorkLoop: skipping cycle due to overload** | Audio HAL I/O thread busy. Common in Simulator or under load. Harmless. |
| **Missing MeshRenderables for ground mesh layer … Tile debug info …** | **MapKit** ground tile / 3D mesh loading. Map may briefly show incomplete tiles; usually recovers. Known Simulator quirk. |
| **RTIInputSystemClient … perform input operation requires a valid sessionID … inputModality = Keyboard** | Keyboard / text input session invalid (e.g. keyboard dismissed). Can appear when switching fields or dismissing quickly. Harmless. |

**Barcode scan doesn’t recognize my boarding pass**

- FlightLedger uses **BCBP** (Bar Coded Boarding Pass). Not all carriers or formats are supported; parsing is best-effort and multi-leg.
- Ensure the barcode is in frame, well lit, and the full code is visible. Try manual entry or OCR (photo) as a fallback.

**OCR (photo) import is wrong or missing fields**

- Results depend on image quality, angle, and font. Use a clear, flat photo of the boarding pass or itinerary.
- The app extracts **departure/arrival** (3-letter codes) even when they’re not in the sample airport list; **date** (multiple formats) and **flight number** (e.g. CA1234, CZ3001) are also detected. If text is split across lines, a full-text pass is used as fallback.
- You can correct the extracted fields in the confirmation step before saving. Using **airports.csv** (OurAirports) in `Resources/Airports/` improves IATA matching and map display (global coverage).

**Airport or country not found / wrong**

- Airport data comes from `Resources/Airports/` (`airports.csv` or `airports_sample.csv`). For full global coverage (including Chinese airports), use OurAirports **airports.csv** (see README “Next steps”).
- “Visited countries” is derived from flight airports and the loaded airport list; missing airports can affect the count.

**Map doesn’t show my flights**

- Confirm flights are saved (check the **Flights** list on the Home tab).
- Use the **year filter** on Home if you’ve filtered by year; the map uses the same filtered set.
- Ensure **Camera** permission is granted if you rely on scan/OCR to add flights.

### Data & privacy

- By default, the app **does not** store raw scan/OCR images; only structured flight data (e.g. route, date, flight number) is persisted.
- You can delete individual flights from the list. Data is stored on device (SwiftData); there is no built-in cloud sync unless you add it (e.g. CloudKit).

---

## FAQ

**What is FlightLedger?**

- An iOS app to record flights (via barcode scan, OCR, or manual entry) and view them in a list and on a world map. It’s built as a SwiftUI + SwiftData skeleton you can extend.

**Which boarding pass formats are supported?**

- **BCBP** (Bar Coded Boarding Pass) in barcode form; multi-leg is supported on a best-effort basis. Other formats are not officially supported; use OCR or manual entry.

**Can I use it without XcodeGen?**

- Yes. Create a new iOS 17+ SwiftUI app in Xcode, then add the `Sources/` and `Resources/` folders to the project and configure the target (e.g. Camera capability, bundle ID). See README “Quick start” for a short outline.

**Where is my data stored?**

- On the device only, using SwiftData (local persistence). No data is sent to a server by the default app.

**Minimum iOS version?**

- iOS 17.0 or later.

---

## Reporting bugs

When reporting a problem, please include:

1. **What you did** (e.g. “Scanned a boarding pass”, “Ran on simulator”).
2. **What you expected** (e.g. “One flight added”, “Map shows route”).
3. **What actually happened** (e.g. “No flight saved”, “App crashed”).
4. **Environment:** Xcode version, iOS version (device or simulator), and whether you used XcodeGen or a manual project.
5. **Exact error message** (if any), e.g. from Xcode or the device.

---

## Contributing

- Check the [README](README.md) for project layout and suggested next steps.
- If you have a patch or feature, follow the project’s contribution process (e.g. pull request or issue discussion) if one is documented.

---

*Last updated for FlightLedger skeleton (iOS 17+, SwiftUI, SwiftData).*
