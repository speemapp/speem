# SPEEM  
**Simple Polkadot E-payments & Exchanges for Mobile**  
*Secure, peer-to-peer DOT transfers & swaps on iOS & Android*

⚠️ **Proof of Concept — Work in Progress** ⚠️  
This repository contains an early prototype of SPEEM. Features, APIs and UX will evolve rapidly. No contributions are being accepted at this stage.

---

## About SPEEM

SPEEM is a minimal mobile application demonstrating cross-platform payments on the Polkadot network. It consists of:

- **Rust core** (`speem-core`):
  - Invoice serialization (JSON ↔ QR)
  - Substrate RPC via `subxt` or `substrate-api-client`
  - UniFFI bindings for Swift & Kotlin

- **iOS shell** (SwiftUI):
  - Camera-based QR scanning
  - Secure key storage (Keychain/Secure Enclave)
  - SwiftUI views for invoice display & payment confirmation

- **Android shell** (Kotlin/Compose):
  - ZXing or ML Kit for QR scanning
  - Android Keystore for key management
  - Jetpack Compose for UI

---

## PoC Workflow

1. **Merchant** enters payment details (recipient address, amount, memo) and **generates** a QR code via the Rust core crate.
2. **Payer** scans the QR code in SPEEM, reviews the invoice, taps **Pay**.
3. Rust core **builds**, **signs** and **submits** the transaction.
4. Both parties receive a **finality notification** once the transfer is included on chain.

---

## Getting Started

```bash
git clone https://github.com/speemapp/speem.git
cd speem

# Build the Rust core
cd core && cargo build

# Open the iOS shell
open ../ios/Speem.xcodeproj

# Open the Android shell
open ../android

---

## Roadmap
- **Phase 1 (PoC)**: Invoice QR generation & scan, basic transaction submission
- **Phase 2**: Finality subscription & push notifications
- **Phase 3**: Key management screens & UX polish
- **Phase 4**: App Store & Play Store distribution, licensing

---

## About the Developer
Created by [Wassim Mansouri](https://wassimans.com) || [LinkedIn](https://www.linkedin.com/in/wassimans/).
Explore the code on [GitHub](https://github.com/speemapp) or visit [speem.app](https://speem.app) for updates.

---

© 2025 SPEEM. All rights reserved.
