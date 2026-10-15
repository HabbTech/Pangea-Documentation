# Firmware Updates

**Settings → Firmware Updates**

Your radio runs Meshtastic firmware. Pangea can check which version it has, download a newer one, and in many cases install it for you. This screen is in Settings with or without Expert Mode.

- [What the screen shows](#what-the-screen-shows)
- [Choosing a version](#choosing-a-version)
- [Installing](#installing)
- [Bootloader and Factory Erase (nRF52 radios)](#bootloader-and-factory-erase-nrf52-radios)
- [Firmware that's too old](#firmware-thats-too-old)
- [Troubleshooting](#troubleshooting)

## What the screen shows

Connect your radio first. The top of the screen shows a picture of the radio and:

| Row | Meaning |
|---|---|
| **Current Firmware Version** | What the radio runs now |
| **Architecture** | The radio's chip family, like nRF52 or ESP32. This decides how updates are installed. |
| **Platform IO** | The exact build target for your board |
| **Intended LoRa Region** | The region set on the radio. Set one before installing firmware. |
| **Suggested file pattern** | The file name to look for if you install by hand |

## Choosing a version

Pick a list at the top of **Firmware Releases**:

| List | What's in it |
|---|---|
| **Stable** | Tested releases. Use this. |
| **Alpha** | Early releases. May have bugs. Use on a spare radio. |
| **Nightly** | Daily builds. For testing only. |
| **Downloaded** | Files you've already downloaded to this device |

Tap **Download** next to a version, then **Install** once it's downloaded. If a version says **Not built for this device**, it has no file for your radio.

You can also tap **Open Local File...** to install a firmware file you already have.

## Installing

Before you start, Pangea shows an **Update Warning**:

- Charge the radio, or plug it into power.
- Keep it close to your phone or Mac.
- Don't close Pangea until it's done.
- Make sure you picked the right firmware.

Tap **I Know What I'm Doing** to go on. The radio disconnects during the update and reconnects when it restarts.

Each version can have more than one file. The tag next to it tells you how it installs:

| Tag | Radios | How it installs |
|---|---|---|
| **ZIP** | nRF52 (RAK4631, T1000-E, ThinkNode M1 and others) | Over Bluetooth, from the app. Tap **Begin Update** and wait. |
| **UF2** | nRF52 and RP2040 | Over USB. Put the radio in update mode (double-press reset), plug it in, tap **Save Firmware to USB**, and save the file to the radio's drive. An error saying the file couldn't be saved is normal: the radio disconnects as soon as it updates. |
| **BIN** | ESP32 (Heltec, T-Beam and others) | Use the web flasher on a computer. Wi-Fi and Bluetooth updates are offered for advanced users, but only work on firmware that already has the right updater installed. |

While a Bluetooth update runs, you can play **Chirpy Hop** without leaving the screen. Progress stays visible above the game.

If you leave the screen mid-update, Pangea asks **Stop the update?** The radio stays in update mode until the update finishes or you turn it off and on again.

## Bootloader and Factory Erase (nRF52 radios)

For supported nRF52 radios, a **Maintenance** section appears at the bottom.

**Upgrade Bootloader** installs the OTAFIX bootloader, which makes Bluetooth updates faster and more reliable.

1. Put the radio in update mode and plug it in by USB. It shows up as a drive.
2. Tap **Choose Bootloader Drive** and pick it. Pangea reads the board type from the drive.
3. Tap **Install Bootloader Update**. The radio installs it and restarts on its own.

**Factory Erase** wipes the radio: its owner, channels, keys, settings, Bluetooth pairings and node list. Use it before you give a radio away, or to rescue a radio that won't start.

1. Put the radio in update mode and plug it in by USB.
2. Tap **Choose Bootloader Drive** and pick it.
3. Tap **Erase This Radio**, then **Erase Everything**.

On a recent bootloader the firmware stays, and the radio starts up as new when you unplug it. On older bootloaders the firmware is removed too, so install firmware next.

> [!WARNING]
> Factory Erase can't be undone. The radio gets new encryption keys, so people you message privately need to swap keys with it again. Your groups are gone from the radio, so you'll need new invites.

In both cases Pangea checks the download before writing anything. If the drive isn't recognized, nothing is written.

## Firmware that's too old

| Firmware | What happens |
|---|---|
| Older than 2.5.14 | Pangea shows **Update Your Firmware** and blocks everything else until you update. The radio stays connected so you can update it from that screen, or tap **Disconnect** to use another radio. |
| Older than the recommended secure version | Pangea shows **Security Update Recommended**. You can keep using the radio, but you should update. |

Private messages need firmware 2.5.18 or newer. See [Supported hardware](../supported-hardware.md#requirements).

## Troubleshooting

**The update stopped partway**
- Keep the radio within 1 to 2 m of your phone and try again.
- If the radio won't start, put it in update mode and install over USB, or use the web flasher on a computer.

**The version shows as Unknown**
Give the radio 5 to 10 seconds after connecting to send its details.

**The release list is empty**
The list needs an internet connection. Leave the screen and open it again once you're online.
