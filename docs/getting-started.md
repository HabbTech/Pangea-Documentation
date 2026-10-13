# Getting Started

From a sealed box to your first message in about five minutes.

- [What you need](#what-you-need)
- [1. Install the app](#1-install-the-app)
- [2. Pair your radio](#2-pair-your-radio)
- [3. Set up your profile](#3-set-up-your-profile)
- [4. Send your first message](#4-send-your-first-message)
- [5. Start a group](#5-start-a-group)
- [Next steps](#next-steps)

## What you need

| | |
|---|---|
| A radio | Running Meshtastic firmware **2.5.18 or newer**. See [Supported hardware](supported-hardware.md). |
| An iPhone, iPad or Mac | iOS 17.5 or newer, or macOS 14.5 or newer, with Bluetooth on. |
| Someone to talk to | Another person with a radio in range, or radios in between to relay. |

> [!TIP]
> Charge the radio before you start. Some radios won't show up over Bluetooth on a flat battery.

## 1. Install the app

Pangea is in testing. Install it from the TestFlight invite you were sent.

## 2. Pair your radio

1. Turn the radio on.
2. Open Pangea. Radios nearby appear in a list within a few seconds.
3. Tap your radio.
4. If your phone asks for a **pairing code**:
   - Radios **with a screen**: type the 6-digit number shown on the radio.
   - Radios **without a screen**: type `123456`.

That's the only time you'll be asked. After the first connection Pangea switches the radio to pair without a code, so reconnecting, pairing again later, or pairing another phone won't ask.

Pangea then sets up the radio for you:

| Setting | What Pangea does |
|---|---|
| **Region** | Picks the legal radio band for the country your phone is set to. If it can't tell, it asks. |
| **Name** | Replaces the factory name (`Meshtastic 1a2b`) with the name you choose in the next step. |
| **Pairing code** | Turns it off after the first connection. |

> [!NOTE]
> Setting the region makes the radio restart once. Pangea reconnects on its own.

## 3. Set up your profile

Choose a name, and optionally an emoji, a color and a photo.

- **Name** is saved to your radio too, so people on other Meshtastic apps see it.
- **Emoji and color** show when you don't have a photo.
- **Photo** is only sent to people you message and groups you're in, and only when they choose to download it.

You can change any of this later: open **Settings** and tap your name at the top.

## 4. Send your first message

Everyone has a personal code. Yours is at the bottom of **New Message** under **Your code**, with **Show QR** and **Share** buttons.

To message someone:

1. Open **Chats**, tap the compose button, then **New Message**.
2. Do one of these:
   - Type their code, like `@4KQ2-F9MX`.
   - Tap the QR button and scan their code.
   - Tap a contact under **Contacts**.
   - Open a link they sent you.
3. Tap **Start Chat**. Tapping a contact opens the chat right away.

The first time you message someone, Pangea says hello over the mesh to swap encryption keys. They need their radio on and in range for that. Scanning their QR code or opening their link works instantly, even from far away.

## 5. Start a group

1. In **Chats**, tap the compose button, then **New Group**.
2. Give it a name (up to 11 characters).
3. Invite people with the QR code, a share link, their code, or from your contacts.

Each group has its own private key. Only people you invite can read it.

## Next steps

- [Messaging](messaging.md): everything about chats, groups and delivery status
- [Contacts & Profiles](contacts-and-profiles.md): photos, nicknames and saved contacts
- [Troubleshooting](troubleshooting.md): if a message doesn't go through
