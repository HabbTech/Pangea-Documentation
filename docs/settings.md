# Settings & Expert Mode

- [Standard settings](#standard-settings)
- [Battery modes](#battery-modes)
- [Expert Mode](#expert-mode)

## Standard settings

| Setting | Where | What it does |
|---|---|---|
| Your profile | **Settings** → your name | Name, emoji, color, photo |
| Your code | **Settings** or **New Message** | Copy, share or show your QR code |
| My Radio | **Settings** | Connected radio, **Pair a Different Radio**, **Forget This Radio** |
| Channels | **Settings → Channels** | See the channels on your radio |
| Share QR Code | **Settings → Share QR Code** | Share your radio's channel setup |
| Display | **Settings → Display** | Radio screen options |
| App Settings | **Settings → App Settings** | Battery mode, Expert Mode, clearing old radios |
| About | **Settings → About** | Version and links |

### Forget This Radio

Disconnects the radio and removes its chats, pending invites and unsent changes from this device. Contacts and your profile stay. You can pair it again any time.

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

Expert Mode shows everything the radio can do: LoRa settings, security, Bluetooth, device role, network, position, power, MQTT, telemetry, and every firmware module. It also adds the **Connect**, **Nodes** and **Mesh Map** tabs, and replaces **Chats** with the full Messages view.

> [!WARNING]
> Expert settings write straight to the radio. A wrong LoRa or channel setting can cut your radio off from everyone else. Leave Expert Mode off unless you know what a setting does.

What's different with Expert Mode on:

| | Standard | Expert Mode |
|---|---|---|
| Messages tab | **Chats** | **Messages** (channels and direct messages) |
| Extra tabs | None | Connect, Nodes, Mesh Map |
| Radio settings | The few most people need | All of them |
| Pairing code | Turned off after first pairing | Left as you set it |
| Radio-side channel mute | Ignored | Honored |
| Connection indicator | Banner at the bottom | Top-right of each screen |
