# Souji（掃除）

**Reclaim your Mac.**

Free, open-source Mac cleaner and app uninstaller. No subscription, no telemetry, no upsell.

[English](README.md) · [繁體中文](docs/README.zh-Hant.md) · [日本語](docs/README.ja.md) · [한국어](docs/README.ko.md)

![Latest Release](https://img.shields.io/github/v/release/anthonytsai68/souji?style=flat-square&label=Download)
![macOS 13.0+](https://img.shields.io/badge/macOS-13.0+-blue?style=flat-square)
![MIT License](https://img.shields.io/github/license/anthonytsai68/souji?style=flat-square)
![No telemetry](https://img.shields.io/badge/telemetry-none-success?style=flat-square)

> **Souji（掃除）** is Japanese for "cleaning" — and that's exactly what it does. Forked from [PureMac](https://github.com/momenbasel/PureMac), Souji is a native SwiftUI macOS cleaner with multilingual support (English, 繁體中文, 日本語, 한국어).

[Install](#install) · [Why](#why-this-exists) · [Features](#what-it-does) · [Compare](#how-it-compares)

## Install

```
brew install --cask souji
```

Or download the signed `.dmg` from [Releases](https://github.com/anthonytsai68/souji/releases/latest).

## Why this exists

Apple sells base-model Macs with 256 GB SSDs you can't upgrade. Most Mac cleaners are subscription apps with telemetry and fear-based scans. Souji is the opposite.

## How it compares

| | **Souji** | CleanMyMac |
|---|---|---|
| Price | **Free** | $40+/yr |
| Open source | **Yes (MIT)** | No |
| Telemetry | **None** | Yes |
| Subscription | **None** | Yes |
| App uninstaller | **Yes** | Yes |
| Trash-only | **Yes** | Partial |
| Languages | 4 | Varies |

## What it does

- **App Uninstaller** — 10-level matching to find every file an app left behind
- **Orphan Finder** — surfaces leftovers from deleted apps
- **Smart Cleaner** — system junk, caches, Xcode, Homebrew, npm, Docker, mail attachments
- **Scheduled Cleaning** — configurable auto-clean
- **Privacy First** — zero telemetry, no network calls

## Languages

Souji supports 4 languages — switch anytime in Settings:
- English
- 繁體中文
- 日本語
- 한국어

## License

MIT. See [LICENSE](LICENSE). Based on [PureMac](https://github.com/momenbasel/PureMac).

---

Short links by [wow.to](https://wow.to)
