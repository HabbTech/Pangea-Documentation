# Nodes

The **Nodes** tab lists every radio your radio has heard. It's added to the tab bar when Expert Mode is on. In this guide, a "node" is any radio on the mesh.

- [The node list](#the-node-list)
- [Finding and filtering](#finding-and-filtering)
- [Quick actions](#quick-actions)
- [Node details](#node-details)
- [Logs and charts](#logs-and-charts)
- [Nodes not heard on your current settings](#nodes-not-heard-on-your-current-settings)
- [Trace routes](#trace-routes)
- [Changing the layout](#changing-the-layout)

## The node list

Each row shows a colored circle with the node's short name, then its long name. Depending on your layout, it can also show:

| Item | Meaning |
|---|---|
| Last heard | When your radio last heard from it |
| Battery | The node's battery level, or a plug if it's powered |
| Lock | A closed lock means you can send it a private message. An open lock means your radio doesn't have its key yet. A crossed-out key means its key changed. |
| Hops away | How many radios passed its messages along to reach you. None means you hear it directly. |
| Signal | Signal quality, for nodes heard directly. See [Signal Meter](signal-meter.md). |
| Distance and bearing | How far away it is and in which direction, if you both share a location |
| Channel | A number if it's on one of your extra channels |
| Role | What the node does on the mesh, like Client or Router |
| Log icons | What kinds of data it has sent, like position or sensor readings |

> [!NOTE]
> A crossed-out key (**Public Key Mismatch**) means the node is using a different key than before. That's normal after someone resets their radio. If you didn't expect it, check with them another way before you trust it.

## Finding and filtering

Type in **Find a node** at the top to search by name.

Tap the filter button for more. The filters are the same as on the map: **Via Lora**, **Via Mqtt**, **Online**, **Hide Not Heard on Current LoRa**, **Encrypted**, **Favorites**, **Ignored**, **Environment**, **Distance**, **Hops Away** and **Roles**. See [Map filters](map.md#filters) for what each one does.

## Quick actions

Long-press a node (right-click on Mac):

| Action | What it does |
|---|---|
| Favorite | Stars it and keeps it at the top |
| **Display name** | Gives it a name only you see. It's never sent over the mesh. |
| **Status Message** | On your own radio only: sets a short status other radios can see (firmware 2.8 or newer) |
| Mute | Silences notifications from this node |
| **Message** | Opens a private chat |
| **Trace Route** | Finds the path to this node. See [Trace routes](#trace-routes). |
| Ignore | Hides it and ignores its messages |
| **Remove** | Deletes it from this device's list. It comes back if it's heard again. |

> [!WARNING]
> If your radio's role is **Client Base**, only favorite nodes you own. Favorites change how a Client Base radio relays, and starring other people's nodes hurts the local mesh.

## Node details

Tap a node to open its details.

**Node** shows its name, node number, ID, public key, firmware, role, and when it was first and last heard. If there's no public key yet, you'll see **No Public Key**. Tap **Exchange User Info** to ask for it.

Below that, sections appear only when the node sends that data: **Environment** (temperature, humidity and more), **Air Quality**, and **Power**.

**Actions:**

| Action | What it does |
|---|---|
| **Share Contact** | Shows a QR code someone can scan to add this node |
| **Message** | Opens a private chat |
| **Exchange Positions** | Sends your location and asks for theirs |
| **Exchange User Info** | Sends your radio's details and asks for theirs, including their key |
| **Request Local Stats** | Asks the node for its radio stats. Choose **Shared channel** for normal use, or **Remote admin**, which needs the node's key. |
| **Trace Route** | Finds the path to this node |
| **Open Compass** | Points you toward the node (iPhone, when it shares a precise location) |
| **Navigate to node** | Opens directions in Maps |
| **Foxhunt on your watch** | Sends the node to your Apple Watch. See [Apple Watch](apple-watch.md). |
| Ignore, **Delete Node** | Hide it, or remove it from this device |

When you can manage a node, like your own radio, an **Administration** section can show **Refresh device metadata** and **Power Off**.

The **I want one** section, when shown, has links to buy that radio model.

## Logs and charts

The **Logs** section opens history the node has sent. Each log has a chart and a table. Tap **Save** to export it as a CSV file, or **Clear Log** to delete it from this device.

| Log | What's in it |
|---|---|
| **Device Metrics Log** | Battery, voltage, channel use and airtime |
| **Node Map** | Where the node has been. Tap **Estimate Coverage** to see how far it can reach. See [Coverage estimate](map.md#coverage-estimate). |
| **Position Log** | Every location it has sent |
| **Environment Metrics Log** | Temperature, humidity, pressure and other sensor readings |
| **Air Quality Metrics Log** | PM1.0, PM2.5 and PM10 |
| **Power Metrics Log** | Voltage and current from a power sensor |
| **Detection Sensor Log** | Motion or door alerts |
| **Local Stats Log** | Packets sent, received, relayed and dropped, and the noise floor |
| **Trace Route Log** | Trace routes to this node |

Only logs with data are shown. See [Telemetry & Sensors](telemetry.md) for what the numbers mean.

## Nodes not heard on your current settings

When you change your radio's preset, region or frequency slot, it moves to a different channel. Nodes it heard before may not be reachable any more.

On firmware 2.8.1 or newer, those nodes show **Not heard on current LoRa**. That's separate from online or offline. Nodes known only through MQTT are never marked.

When most of the list is like this, a notice offers two choices:

- **Remove Them** removes those nodes from Pangea and from the radio. Favorites and your own radio are kept. Any that are still around come back when they're heard again.
- **Keep** hides the notice until more nodes join the count.

Nothing is removed unless you choose to.

## Trace routes

A trace route shows which radios a message passes through to reach a node, and the signal on each hop.

Start one from a node's **Trace Route** action. Radios limit how often you can run one, so the button counts down before you can run another. Results arrive in a few seconds to a minute.

All your results are in **Settings → Logging → Trace Routes**. Tap one and choose **Show on Map** to see it drawn out. See [Trace routes on the map](map.md#trace-routes-on-the-map).

## Changing the layout

**Settings → App Settings → Node Layout**

| Setting | Options |
|---|---|
| **Node List Density** | **Complete** shows everything. **Compact** shows less, so more nodes fit. |
| Compact fields | Choose which items Compact shows: **Power**, **Last Heard Time**, **Relative Last Heard Time**, **Distance and Bearing**, **Hops Away**, **Signal (Direct Only)**, **Channel**, **Device Role**, **Log Icons** |

**Clear Stale Nodes** in **App Settings** removes nodes you haven't heard from in a while. Favorites and ignored nodes are always kept.
