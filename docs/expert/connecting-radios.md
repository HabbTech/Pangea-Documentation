# Connecting Radios

With Expert Mode on, the **Connect** tab shows the radio you're connected to and lets you connect over Bluetooth, Wi-Fi or USB.

- [The Connect tab](#the-connect-tab)
- [Connection types](#connection-types)
- [Disconnect and Power Off](#disconnect-and-power-off)
- [Mesh Live Activity](#mesh-live-activity)
- [Switching radios](#switching-radios)
- [Bluetooth settings](#bluetooth-settings)
- [Troubleshooting](#troubleshooting)

## The Connect tab

When a radio is connected, the top of the tab shows:

| Row | What it tells you |
|---|---|
| **Connection Name** | The radio's Bluetooth or network name |
| **Firmware Version** | The firmware running on the radio |
| **Preset** | The LoRa preset the radio is using, like Long Range - Fast |
| Status | **Communicating**, **Retrieving nodes**, **Subscribed** (ready), or **Retrying** |

If the radio has no region set, a red **Set LoRa Region** button appears. Tap it to pick one.

When nothing is connected, the tab lists **Available Radios**. Tap one to connect. Each row shows a signal bar for how strong the radio's Bluetooth signal is.

## Connection types

| Type | iPhone / iPad | Mac | How to connect |
|---|---|---|---|
| Bluetooth | Yes | Yes | Tap the radio under **Available Radios** |
| Wi-Fi / TCP | Yes | Yes | Tap **Manual** → **TCP**, then type the radio's address, like `192.168.1.50` or `radio.local:4403` |
| USB serial | No | Yes | Plug the radio in. It appears under **Available Radios**. |

Radios you add by address are saved under **Manual Connections**. Swipe left to delete one (right-click on Mac).

Some radios can be put on Wi-Fi from the app. When one is nearby, it shows under **Wi-Fi Setup**. Tap it and follow the steps.

## Disconnect and Power Off

| Action | iPhone / iPad | Mac | What happens |
|---|---|---|---|
| **Disconnect** | Swipe left on the radio, or long-press → **Disconnect** | Right-click → **Disconnect**, or the **Disconnect** button | Pangea stops talking to the radio. The radio keeps running on the mesh. |
| **Power Off** | Long-press → **Power Off** | Right-click → **Power Off** | The radio shuts down. You have to turn it back on by hand. |

Power Off asks you to confirm first. Be careful with radios on a roof or a pole.

The long-press menu also has **Share Contact**, which shows a QR code other people can scan to add your radio.

## Mesh Live Activity

On iPhone, long-press the connected radio and tap **Mesh Live Activity** to show mesh status on the Lock Screen and in the Dynamic Island. Tap it again to stop.

Live Activities are turned off in the **Expedition** battery mode. See [Battery modes](../settings.md#battery-modes).

## Switching radios

You can pair several radios, but only one is connected at a time. Disconnect, then tap a different radio under **Available Radios**.

Pangea keeps a separate copy of each radio's nodes and messages. When you switch, it saves the old radio's data and loads the new one's. The screen shows a spinner until that's done.

## Bluetooth settings

**Settings → Bluetooth** (shows **Expert Mode** under the name)

| Setting | What it does |
|---|---|
| Enabled | Turns the radio's Bluetooth on or off. If you turn it off, you can only reach the radio over Wi-Fi or USB. |
| Pairing mode | **Random Pin** shows a new code on the radio's screen. **Fixed Pin** uses a 6-digit code you choose. **No PIN (Just Works)** pairs without a code. |
| Fixed Pin | The 6-digit code, when Pairing mode is **Fixed Pin** |

Without Expert Mode, Pangea switches radios to **No PIN** after the first pairing. With Expert Mode on, Pangea leaves this setting as you set it. See [Bluetooth pairing](../privacy-and-security.md#bluetooth-pairing).

## Troubleshooting

**The radio isn't listed**
- If you see **Bluetooth is off**, tap it to open Settings and turn Bluetooth on.
- Move closer. Bluetooth reaches about 10 m (30 ft).
- Close other Meshtastic apps. A radio talks to one app at a time.
- Restart the radio.

**The connection keeps dropping**
- Charge the radio.
- Forget the radio in the system Bluetooth settings, then connect again from Pangea.

**It says Retrying**
Pangea tries a few times on its own. If it doesn't connect, restart the radio and try again.

More fixes are in [Troubleshooting](../troubleshooting.md#my-radio-doesnt-show-up).
