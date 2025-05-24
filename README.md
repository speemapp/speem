# SPEEM  
**Secure Peer-to-peer Encrypted Electronic Money**
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

``` mermaid
sequenceDiagram
    participant U as User App
    participant M as Merchant App
    participant Core as Rust Core
    participant Net as Polkadot Network
    participant History as Local Storage

    Note over U: **Onboarding / Wallet Setup**
    U->>U: Launch App
    U->>U: Scan or Enter Wallet Address
    U->>Core: store_wallet(address)
    Core-->>History: save_wallet(address)

    Note over U,M: **Wallet Sharing**
    M->>Core: generate_wallet_qr()
    Core-->>M: wallet_qr_image
    M->>U: show_wallet_qr
    U->>Core: scan_qr()
    Core-->>U: wallet_address

    Note over M: **Invoice Generation**
    M->>Core: create_invoice(recipient, amount, memo)
    Core-->>Core: serialize & QR encode
    Core-->>M: invoice_qr_image
    M->>History: save_invoice(invoice)

    Note over U: **Invoice Payment**
    U->>U: scan_invoice_qr
    U->>Core: decode_invoice(qr)
    Core-->>U: invoice_details
    U->>U: Confirm Payment
    U->>Core: pay_invoice(details)
    Core->>Net: submit_extrinsic(tx)
    Core-->>History: save_invoice(invoice)

    Note over Core,Net: **Wait for Finality**
    Net-->>Core: finality_event(tx)
    Core-->>M: notify_finality(tx)
    Core-->>U: notify_finality(tx)
```

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

```

---

## Roadmap
- **Phase 1 (PoC)**: Invoice QR generation & scan, basic transaction submission -> **DOING**
- **Phase 2**: Finality subscription & push notifications -> **TODO**
- **Phase 3**: Key management screens & UX polish -> **TODO**
- **Phase 4**: App Store & Play Store distribution, licensing -> **TODO**

---

## About the Developer
Created by [Wassim Mansouri](https://wassimans.com) || [LinkedIn](https://www.linkedin.com/in/wassimans/).
Explore the code on [GitHub](https://github.com/speemapp) or visit [speem.app](https://speem.app) for updates.

---

© 2025 SPEEM. All rights reserved.
