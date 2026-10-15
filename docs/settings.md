# Settings & Expert Mode

- [Standard settings](#standard-settings)
- [Appearance](#appearance)
- [Battery modes](#battery-modes)
- [Expert Mode](#expert-mode)
- [Settings in Expert Mode](#settings-in-expert-mode)

## Standard settings

| Setting | Where | What it does |
|---|---|---|
| Your profile | **Settings** → your name | Name, emoji, color, photo |
| Your code | **Settings** or **New Message** | Copy, share or show your QR code |
| My Radio | **Settings** | Connected radio, **Pair a Different Radio**, **Forget This Radio** |
| Display | **Settings → Display** | Radio screen options |
| App Settings | **Settings → App Settings** | Appearance, battery mode, Expert Mode, clearing old radios |
| Routes | **Settings → Routes** | Routes you've saved or recorded |
| Route Recorder | **Settings → Route Recorder** | Record where you go |
| Firmware Updates | **Settings → Firmware Updates** | Check and update your radio's firmware. See [Firmware Updates](expert/firmware-updates.md). |
| About Pangea | **Settings → About Pangea** | Version and links |

### Forget This Radio

Disconnects the radio and removes its chats, pending invites and unsent changes from this device. Contacts and your profile stay. You can pair it again any time.

## Appearance

**Settings → App Settings → Appearance**

Choose **Light** or **Dark** for Pangea on its own, or **Match Device** to follow your device's setting.

## Battery modes

**Settings → App Settings → Battery**

| Mode | What changes | Good for |
|---|---|---|
| **Standard** | Everything on | Everyday use |
| **Trail** | Smart position only, cached weather, slower map refresh, less frequent Bluetooth check-ins | Day trips |
| **Expedition** | Continuous GPS, weather, Live Activities and background auto-connect off | Multi-day trips |

When iOS Low Power Mode is on, Pangea switches to Expedition until it turns off, then goes back to your choice.

## Expert Mode

**Settings → App Settings → Expert Mode**

Expert Mode shows everything the radio can do: LoRa settings, security, Bluetooth, device role, network, position, power, MQTT, telemetry, and every firmware module. It also adds the **Connect**, **Nodes** and **Map** tabs, and replaces **Chats** with the full Messages view.

> [!WARNING]
> Expert settings write straight to the radio. A wrong LoRa or channel setting can cut your radio off from everyone else. Leave Expert Mode off unless you know what a setting does.

Each screen Expert Mode adds has its own guide. See the [Expert Mode guides](expert/README.md).

What's different with Expert Mode on:

| | Standard | Expert Mode |
|---|---|---|
| Messages tab | **Chats** | **Messages** (channels and direct messages) |
| Extra tabs | None | Connect, Nodes, Map |
| Radio settings | The few most people need | All of them |
| Pairing code | Turned off after first pairing | Left as you set it |
| Radio-side channel mute | Ignored | Honored |
| Connection indicator | Banner at the bottom | Top-right of each screen |

## Settings in Expert Mode

With Expert Mode on, Settings shows every section. Rows that only appear in Expert Mode say **Expert Mode** under their name.

Type in **Search settings** at the top to jump straight to a setting.

| Section | What's in it | Guide |
|---|---|---|
| Top of the list | **About Pangea**, **Help & Documentation**, **App Settings**, **Local Mesh Discovery**, **Routes**, **Route Recorder**, **Firmware Updates** | [Local Mesh Discovery](expert/local-mesh-discovery.md), [Firmware Updates](expert/firmware-updates.md) |
| Configure | Which radio you're changing. With **Administration** on in App Settings, you can pick another radio you have admin access to. | |
| Radio Configuration | **LoRa**, **Channels**, **Security**, **Share QR Code** | |
| Device Configuration | **User**, **Bluetooth**, **Device**, **Display**, **Network**, **Position**, **Power** | [Connecting Radios](expert/connecting-radios.md#bluetooth-settings) |
| Module Configuration | Firmware modules like **MQTT**, **Telemetry**, **Detection Sensor**, **TAK Server**, **Canned Messages**, **Range Test** and **Store & Forward**. Only modules your radio supports are listed. | [MQTT](expert/mqtt.md), [Telemetry & Sensors](expert/telemetry.md), [TAK](expert/tak.md) |
| Backup & Restore | **Export Configuration** saves all of the radio's settings to a file. **Import Configuration** loads them back. | |
| Logging | **Logs** and **Trace Routes** | [Logs & File Storage](expert/logs-and-storage.md), [Nodes](expert/nodes.md#trace-routes) |
| Developers | **App Files** and other tools. Only in test builds, like TestFlight. | [Logs & File Storage](expert/logs-and-storage.md#file-storage) |

> [!WARNING]
> A configuration backup holds your radio's private key, channel keys and Wi-Fi and MQTT passwords. Anyone with the file can join and control your mesh. Keep it private.

In regions with a transmit limit, like EU_868, **Hourly Duty Cycle** appears at the top of Radio Configuration. Your radio stops sending once it hits the hourly limit, so keep automatic reports infrequent.

A radio set up as **managed** can only be changed by a remote admin. Its settings are hidden, and Settings says so.
