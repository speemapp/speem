# ✨ SPEEM - Stack-Powered Elephants Entering the Matrix ✨  
*“When elephants code, the Matrix trembles.”*  

## ⚠️ 🚧 Under Active Development 🚧 ⚠️
The SPEEM project is in early stages—features, docs, and APIs will evolve rapidly.

---

## About SPEEM
SPEEM is a cross‑platform Matrix client built in **Rust** and powered by **Slint**. It delivers a native look & feel, lean binary footprint, and end‑to‑end encrypted messaging on macOS, Windows, and Linux.

---

## Key Technologies
- **Rust Core:** Uses the [matrix-rust-sdk](https://github.com/matrix-org/matrix-rust-sdk) for protocol handling, synchronization, and cryptography.
- **Slint GUI:** GPU‑accelerated, responsive, and native‑feeling interfaces.
- **Modular Monorepo:** Single repo containing all code—core library, and desktop app for simplified dependency management.
- **E2E Encryption:** Full support for Olm & Megolm ensuring privacy.
- **Cross‑Platform Packaging:** One codebase targeting macOS, Windows, and Linux with minimal overhead.

---

## Project Structure (Monorepo)
```
/  
├─ core/         # Rust shared library: Matrix protocol, crypto, sync logic
├─ desktop/      # Desktop client (Rust + Slint) for macOS, Windows, Linux
├─ docs/         # Documentation, design sketches, roadmap
└─ ci/           # CI/CD workflows, linting, formatting configs
```

---

## Features
- **Fast Login & Sync:** Secure authentication and incremental room updates.
- **Persistent Chat History:** Encrypted local storage for messages and media.
- **Rich Text & Markdown:** Support for formatted messages, inline images, and attachments.
- **Group & Direct Chats:** Public rooms, private groups, and DMs.
- **Notifications & Theming:** Desktop notifications, light/dark mode.
- **Modular UI:** Easily extendable widgets and theming powered by Slint.

---

## Development Roadmap

### Proof of Concept
- Basic login & authentication flow
- Room list and message timeline
- Send & receive text messages

### Minimum Viable Product (MVP)
- End-to-end encryption (Olm/Megolm)
- Multimedia attachments & previews
- Room search functionality
- Cross-platform packaging & installers

### Version 1.0
- System integrations: notifications, tray/menu support
- Advanced settings: proxy, custom server URLs
- Performance optimizations & memory tuning
- Accessibility improvements & localization

---

## About the Developer
Created by [Wassim Mansouri](https://wassimans.com).  
Explore the code on [GitHub](https://github.com/speemapp) or visit [speem.app](https://speem.app) for updates.

---

© 2025 SPEEM. All rights reserved.
