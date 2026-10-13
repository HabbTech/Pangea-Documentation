<div align="center">

# Pangea

**Text your friends when there's no cell service.**

Pangea is a messaging app for LoRa mesh radios. Pair a pocket radio with your phone and send messages, share profiles, and chat in groups over miles of open ground, with no towers, no SIM and no internet.

[![iOS](https://img.shields.io/badge/iOS-In%20Testing-f5a623?logo=apple&logoColor=white)](#platform-status)
[![macOS](https://img.shields.io/badge/macOS-Testing-f5a623?logo=apple&logoColor=white)](#platform-status)
[![Android](https://img.shields.io/badge/Android-In%20Development-8e8e93?logo=android&logoColor=white)](#platform-status)
[![Windows](https://img.shields.io/badge/Windows-In%20Development-8e8e93?logo=windows&logoColor=white)](#platform-status)
[![Firmware](https://img.shields.io/badge/radio%20firmware-2.5.18%2B-2ea44f)](docs/supported-hardware.md)

[Getting Started](docs/getting-started.md) ·
[Messaging](docs/messaging.md) ·
[Privacy](docs/privacy-and-security.md) ·
[Hardware](docs/supported-hardware.md) ·
[Troubleshooting](docs/troubleshooting.md) ·
[FAQ](docs/faq.md)

</div>

---

## Platform status

| Platform | Status | Minimum version | Notes |
|---|---|---|---|
| iOS / iPadOS | 🟡 In Testing | iOS 17.5 | Primary platform |
| macOS | 🟡 Testing | macOS 14.5 | Same app as iPhone, built for the Mac |
| Android | ⚪ In Development | n/a | Not available yet |
| Windows | ⚪ In Development | n/a | Not available yet |

🟢 Released 🟡 Testing ⚪ In development

## Features

| | |
|---|---|
| **No-setup pairing** | Pick your radio from a list. Pangea names it, sets the right region for your country, and turns off the pairing code after the first connection. |
| **Personal codes** | Everyone gets a short code like `@4KQ2-F9MX`. Type it, scan it as a QR code, or tap a shared link to start a private chat. |
| **Private messages** | Direct messages are end-to-end encrypted between the two radios. |
| **Group chats** | Up to 7 private groups. Invite people with a link, a QR code, their code, or straight from your contacts. |
| **Everyone Nearby** | The public channel every radio in range can read. Pinned to the top of Chats, notifications off unless you turn them on. |
| **@mentions** | Mention someone in a group and it links to their profile. |
| **Profiles** | A name, an emoji, a color and an optional photo. Friends see your photo only after they choose to download it. |
| **Contacts** | Save people from their profile and find them again in New Message and group invites. |
| **Delivery status** | Every message shows Sending, Delivered or Not delivered, with Try Again when it didn't make it. |
| **Expert Mode** | Opens the full radio configuration for people who want it. Off by default. |

## How it works

```
 Your phone ──Bluetooth── Your radio ))) LoRa ((( Their radio ──Bluetooth── Their phone
                                        │
                              Other radios in range
                              relay messages along
```

Your phone talks to your radio over Bluetooth. The radio sends your message over LoRa, a long-range, low-power radio signal. Other radios that hear it pass it along, up to 3 hops by default, until it reaches the person you're messaging. Nothing goes through the internet.

Range depends on the land and how high the radios sit. A radio in a pocket in town might reach a few hundred meters. Radios on a hilltop or rooftop can reach many kilometers.

## Quick start

1. **Get a radio.** Any radio running Meshtastic firmware 2.5.18 or newer works. See [Supported hardware](docs/supported-hardware.md).
2. **Install Pangea** on your iPhone, iPad or Mac.
3. **Turn the radio on** and open Pangea. Pick your radio from the list.
4. **Enter the pairing code if asked.** This only happens the first time. Use the number on the radio's screen, or `123456` for radios without a screen.
5. **Set your name and photo.**
6. **Message someone.** Tap **New Message** and enter their code, or scan their QR code.

Full walkthrough: [Getting Started](docs/getting-started.md).

## Documentation

| Guide | What's in it |
|---|---|
| [Getting Started](docs/getting-started.md) | Install, pair a radio, set up your profile |
| [Messaging](docs/messaging.md) | Codes, private chats, groups, Everyone Nearby, mentions, delivery status |
| [Contacts & Profiles](docs/contacts-and-profiles.md) | Photos, nicknames, saving contacts |
| [Privacy & Security](docs/privacy-and-security.md) | What's encrypted, what's public, what's sent where |
| [Supported Hardware](docs/supported-hardware.md) | Radios, firmware, regions |
| [Settings & Expert Mode](docs/settings.md) | App settings, battery modes, the full radio configuration |
| [Limits](docs/limits.md) | Message size, group count, photo size and timing |
| [Troubleshooting](docs/troubleshooting.md) | Messages not delivering, pairing problems, missing chats |
| [FAQ](docs/faq.md) | Short answers to common questions |
| [Glossary](docs/glossary.md) | LoRa, mesh, hops, channels and other terms |

## Compatibility

Pangea speaks the open Meshtastic protocol. That means:

- You can message people using other Meshtastic apps. They see your name and messages. Profile photos and emoji only show for people using Pangea.
- Radios set up with Pangea keep working with other Meshtastic apps.
- Pangea's group invites only use private keys, so a group made in Pangea can't be read by someone on the public channel.

## Support

- **Questions and bugs:** open an [issue](../../issues/new/choose).
- **Website:** [habb.tech](https://habb.tech/)

## Acknowledgments

Pangea is built on the [Meshtastic](https://meshtastic.org) project and its open radio firmware and protocol. Meshtastic® is a registered trademark of Meshtastic LLC. Pangea is not affiliated with or endorsed by the Meshtastic project.

---

<div align="center">
<sub>Pangea® Copyright HABB</sub>
</div>
