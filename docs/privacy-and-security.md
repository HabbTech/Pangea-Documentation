# Privacy & Security

Short version: **private messages and groups are encrypted. Everyone Nearby is public.** Everything stays on your device and your radio. There are no Pangea accounts, no servers, and no analytics.

- [What's encrypted](#whats-encrypted)
- [What's visible to others](#whats-visible-to-others)
- [What's stored where](#whats-stored-where)
- [Bluetooth pairing](#bluetooth-pairing)
- [No tracking](#no-tracking)
- [Reporting a security issue](#reporting-a-security-issue)

## What's encrypted

| Traffic | Protection | Who can read it |
|---|---|---|
| Private messages | Public-key encryption between the two radios (Meshtastic PKC, firmware 2.5+) | Only the two of you |
| Private groups | AES with a random 256-bit key created by Pangea | Anyone holding the invite |
| Group invites sent in the app | Sent as an encrypted private message | Only the person invited |
| Profile cards and photos | Sent only over private messages and private groups | The people you share with |
| Everyone Nearby | The well-known default key | **Anyone in range** |

> [!IMPORTANT]
> A group invite link or QR code **is** the key. Anyone who gets it can read the group. Share it the way you'd share a door key.

## What's visible to others

Some information is broadcast by every Meshtastic radio so the mesh can work. It's visible to anyone in range:

| Information | Visible to |
|---|---|
| Your radio's name and short name | Everyone in range |
| Your radio's ID and public key | Everyone in range |
| Radio model, battery and signal reports | Everyone in range |
| Location | Only if location sharing is turned on for your radio |
| Who sent a packet to whom | Relays can see the sender and recipient IDs, not the content |

Your Pangea photo, emoji, color, nicknames and contacts are **not** broadcast.

## What's stored where

| Data | On your device | On your radio | Anywhere else |
|---|---|---|---|
| Messages | ✓ | Briefly, while sending | ✗ |
| Contacts and nicknames | ✓ | ✗ | ✗ |
| Your profile and photo | ✓ | Name only | ✗ |
| Other people's photos | ✓, once downloaded | ✗ | ✗ |
| Group keys | ✓ | ✓ | ✗ |

**Forget radio** (in Settings) removes that radio's chats, invites and pending changes from your device. Your contacts and profile stay.

## Bluetooth pairing

The first connection to a radio uses its pairing code. After that, Pangea switches the radio to pair without a code so it's easy to reconnect.

That means anyone within Bluetooth range (about 10 m / 30 ft) with a Meshtastic app could connect to your radio while your phone isn't connected to it. If that matters for how you use it, set a pairing code again in **Expert Mode → Bluetooth**. Pangea leaves the pairing setting alone while Expert Mode is on.

## No tracking

Pangea doesn't include analytics, crash reporting or session recording.

## Reporting a security issue

Please don't open a public issue. See [SECURITY.md](../SECURITY.md).
