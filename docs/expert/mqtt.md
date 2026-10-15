# MQTT

**Settings → MQTT** (shows **Expert Mode** under the name)

MQTT links your mesh to a server on the internet. A radio with MQTT on sends what it hears to the server, and can bring messages from the server back onto the mesh. Two meshes in different places can then act like one, as long as each has a radio with internet.

Pangea doesn't need MQTT. Messages go radio to radio without it. Leave it off unless you have a reason to use it.

> [!WARNING]
> Anything sent to an MQTT server leaves the mesh and goes over the internet. Traffic on Everyone Nearby, and anything else on a channel with the default key, can be read by anyone on that server.

- [How a radio reaches the server](#how-a-radio-reaches-the-server)
- [Settings](#settings)
- [Choosing which channels go over MQTT](#choosing-which-channels-go-over-mqtt)
- [Map Report](#map-report)
- [Things to know](#things-to-know)

## How a radio reaches the server

| Way | When to use it |
|---|---|
| The radio's own Wi-Fi or Ethernet | Radios with Wi-Fi, set up under **Settings → Network** |
| Through Pangea | Radios without Wi-Fi. Turn on **MQTT Client Proxy** and Pangea passes MQTT traffic through your phone or Mac's internet connection. Pangea has to stay open and connected. |

When the proxy is on and working, the **Connect** tab shows the server and topic in use.

## Settings

| Section | Setting | What it does |
|---|---|---|
| Options | **MQTT Enabled** | Turns MQTT on |
| Options | **MQTT Client Proxy** | Sends MQTT through Pangea instead of the radio's own internet. Once saved, **Connect to MQTT via Proxy** starts and stops the link. |
| Options | **Encryption Enabled** | Sends packets to the server still encrypted. Keep this on. |
| Root Topic | **Root Topic** | The topic messages are filed under. Defaults to `msh/` plus your region. Pangea suggests more local topics if the default one is too busy. |
| Server | **Address** | The server's address. The public server is `mqtt.meshtastic.org`. |
| Server | **Username**, **Password** | For your own server. Hidden for the public server. |
| Server | **TLS Enabled** | Encrypts the connection to the server. The public server doesn't support it. |

Tap **Save** to send the changes to the radio.

## Choosing which channels go over MQTT

Turning MQTT on isn't enough. You also choose, for each channel, whether it goes to the server and comes back from it. Open **Settings → Channels**, tap a channel, and set **MQTT Uplink Enabled** (send to the server) and **MQTT Downlink Enabled** (bring messages back from it).

Only turn on uplink for channels you're happy to send over the internet.

## Map Report

**Map Reporting** sends your radio's name and an approximate location to the server so it can appear on public mesh maps.

To include a location, turn on **Report Location**. Pangea asks you to agree first, because the map report isn't encrypted and others may store and show it. You can choose how often it's sent and how precise the location is. Pangea never sends your exact location here.

## Things to know

- **Duty cycle regions.** In regions that limit how much a radio can transmit, like EU_868, Pangea warns you. MQTT can bring in more traffic than the mesh can carry. Avoid it there.
- **Use your own server for anything private.** The public server is shared by everyone. Use it to test, not for sensitive messages.
- **Radios from MQTT show in your lists.** Radios heard through MQTT appear in **Nodes** and on the **Map**. Use the **Via Lora** and **Via Mqtt** filters to tell them apart.
