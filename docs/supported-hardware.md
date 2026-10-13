# Supported Hardware

Pangea works with any LoRa radio running **Meshtastic firmware 2.5.18 or newer**.

- [Requirements](#requirements)
- [Radios](#radios)
- [Connections](#connections)
- [Regions](#regions)
- [Antennas](#antennas)

## Requirements

| | Minimum |
|---|---|
| Radio firmware | Meshtastic **2.5.18** |
| iPhone / iPad | iOS / iPadOS **17.5** |
| Mac | macOS **14.5** |
| Phone or Mac radio link | Bluetooth LE |

Older firmware connects but can't use encrypted private messages. Update the radio with the [Meshtastic web flasher](https://flasher.meshtastic.org) first.

## Radios

| Radio | Screen | Pairing code | Status |
|---|---|---|---|
| RAK WisBlock (RAK4631) | Optional | `123456` without a screen | ✅ Tested |
| Heltec V3 / V4 | Yes | Shown on screen | Expected to work |
| LilyGO T-Beam | Optional | Shown on screen, or `123456` | Expected to work |
| Seeed SenseCAP T1000-E | No | `123456` | Expected to work |
| Elecrow ThinkNode M1 | Yes | Shown on screen | Expected to work |
| Pangea radios (`PANGEA:ID:…`) | Varies | Set up before shipping | ✅ Supported |

"Expected to work" means the radio runs standard Meshtastic firmware but hasn't gone through Pangea testing yet. If you try one, [let us know](../../../issues/new/choose) how it went.

## Connections

| Connection | iPhone / iPad | Mac |
|---|---|---|
| Bluetooth LE | ✅ | ✅ |
| Wi-Fi / TCP | Expert Mode | Expert Mode |
| USB serial | ✗ | Expert Mode |

## Regions

LoRa radios have to use the frequency band that's legal where you are. Pangea picks it from your phone's region setting the first time you pair:

| Region | Band | Countries (examples) |
|---|---|---|
| US | 902–928 MHz | United States, Canada, Mexico, Puerto Rico |
| EU_868 | 869.4–869.65 MHz | EU and EEA, UK, Switzerland, Norway, Türkiye, South Africa |
| ANZ | 915–928 MHz | Australia, New Zealand, Brazil, Chile, Argentina, Colombia |
| JP | 920.5–923.5 MHz | Japan |
| KR | 920–923 MHz | South Korea |
| TW | 920–925 MHz | Taiwan |
| CN | 470–510 MHz | China |
| IN | 865–867 MHz | India |
| TH | 920–925 MHz | Thailand |
| RU | 868.7–869.2 MHz | Russia |
| UA_868 | 868–868.6 MHz | Ukraine |
| MY_919 | 919–924 MHz | Malaysia |
| SG_923 | 917–925 MHz | Singapore |
| PH_915 | 915–918 MHz | Philippines |
| KZ_863 | 863–868 MHz | Kazakhstan |

If your country isn't listed, Pangea asks you to choose. Radios only talk to radios on the same region and settings.

## Antennas

The antenna matters more than anything else for range.

- **Never power on a radio without its antenna.** It can damage the radio.
- Use an antenna made for your band (for example 915 MHz in the US).
- Some boards have two antenna sockets. On the RAK4631 the LoRa antenna goes on the socket marked **LoRa**, not **BLE**.
- Height beats power. A radio on a windowsill or a pack strap reaches much farther than one in a pocket.
