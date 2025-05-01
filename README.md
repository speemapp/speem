# 🐘 SPEEM App

## ⚠️ 🚧 Under Active Development 🚧 ⚠️
This project is in early stages—features, APIs, and UX will evolve rapidly. Breaking changes may occur.

---

## About SPEEM App

SPEEM App is the Rust & Iced–powered client of **✨ Stack-Powered Elephants Entering the Matrix ✨**. It delivers a native-feeling, cross-platform Matrix experience on macOS, Windows, and Linux with minimal binary footprint.

---

## Key Technologies

- **Rust Core:** Built atop the [matrix-rust-sdk](https://github.com/matrix-org/matrix-rust-sdk) for Client–Server API, synchronization, and encryption (Olm/Megolm).
- **Iced GUI:** GPU-accelerated, immediate-mode UI toolkit for responsive, native-style interfaces.
- **Async Runtime:** Uses [Tokio](https://tokio.rs/) and `futures` for efficient networking and concurrency.
- **Modular Monorepo:** This desktop app lives under `desktop/` alongside other SPEEM modules for unified development.

---

## Features

- **Secure Login & Sync:** Sign in with Matrix credentials and sync rooms incrementally.
- **Room List & Timeline:** Browse joined rooms and view message history.
- **Send & Receive Messages:** Real-time text chat with secure handling.
- **End-to-End Encryption:** Full support for Olm and Megolm protocols.
- **Rich Content:** Markdown rendering, inline images, and file attachments.
- **Theming & Notifications:** Light/dark mode toggle and native desktop alerts.

---

## Getting Started

1. Clone the monorepo:
   ```bash
   git clone https://github.com/speemapp/speem.git
   cd speem/desktop
   ```
2. Build and run:
   ```bash
   cargo run --release
   ```
3. Configure via `config.toml` (create one beside the binary):
   ```toml
   server_url = "https://matrix.org"
   username = "@alice:matrix.org"
   password = "••••••"
   ```

---

## Project Structure

```
desktop/
├─ src/           # Rust source code for the desktop client
├─ assets/        # Icons, stylesheets, and UI assets
├─ config.toml    # Default configuration template
└─ Cargo.toml     # Desktop app manifest
```

---


## License

Apache-2.0 OR MIT

---

*“When elephants code, the Matrix trembles.”*
