# Map & Waypoints

The **Map** tab shows every radio that has shared its location. Expert Mode adds the buttons, filters, waypoints and node details below. For the basics, see [Map](../map.md).

- [Reading the map](#reading-the-map)
- [Map buttons](#map-buttons)
- [Filters](#filters)
- [Map Options](#map-options)
- [Offline maps](#offline-maps)
- [Waypoints](#waypoints)
- [Geofences](#geofences)
- [Coverage estimate](#coverage-estimate)
- [Trace routes on the map](#trace-routes-on-the-map)

## Reading the map

- Each radio with a location is a colored circle with its short name. Tap it for its name, when it was last heard, its signal, and a shortcut to message it.
- Radios that share an approximate location get a see-through circle showing the area they could be in.
- When several radios are at the same spot, tap the stack to pick one from a list.
- The map opens where you last left it.

Many radios have no GPS or keep location off, so they never appear. Radios that do share it usually send it every 15 to 30 minutes.

## Map buttons

The buttons sit in the bottom-right corner.

| Button | What it does |
|---|---|
| Signal bars | Opens [Estimate Coverage](#coverage-estimate) |
| Funnel | Opens [Filters](#filters). It's filled in when a filter is on. |
| Map | Shows the legend for trace routes |
| ⓘ | Opens [Map Options](#map-options) |

On Mac there's also a button to open the map in its own window.

## Filters

Filters change which radios the map shows. The Nodes tab uses the same filters.

| Filter | Shows only |
|---|---|
| **Via Lora** | Radios heard over the air |
| **Via Mqtt** | Radios heard through an internet bridge. See [MQTT](mqtt.md). |
| **Online** | Radios heard in the last 2 hours |
| **Hide Not Heard on Current LoRa** | Hides radios your radio hasn't heard on its current settings (firmware 2.8.1 or newer) |
| **Encrypted** | Radios that support private messages |
| **Favorites** | Radios you've starred |
| **Distance** | Radios within a distance of you |
| **Hops Away** | Radios within a number of hops. 0 means direct. |
| **Roles** | Radios with the roles you pick, like Client or Router |

To see who you can reach directly, turn on **Via Lora** and turn off **Via Mqtt**.

## Map Options

| Option | What it does |
|---|---|
| Standard, Hybrid, Satellite | The base map style |
| **Waypoints** | Show or hide waypoints |
| **Precise Locations Only** | Hide radios that share an approximate location |
| **Cluster Nodes** | Group nearby radios into one numbered pin. Tap it to zoom in. |
| **My Location** | Show or hide your own blue dot |
| **Convex Hull** | Draw an outline around your outermost radios, to show how far the mesh reaches |
| **Traffic** | Apple Maps traffic |
| **Points of Interest** | Apple Maps places |

**Map Overlays** lists map files you've added. Tap **Upload Map Data** to add a GeoJSON file. Each file has its own switch. Swipe left to delete one.

## Offline maps

Under **Offline Maps** in Map Options:

- Tap **Offline Maps** to download an area. Pick it on the map and download it while you have internet.
- **Offline Tiles** shows your downloaded maps when you have no connection. They also turn on by themselves when your phone is offline.
- **Hillshade** adds shaded terrain over downloaded areas.
- **Contour Lines** adds elevation lines over downloaded areas.

Download offline maps before you head out. Without internet, areas you didn't download show blank.

## Waypoints

A waypoint is a named pin you can share with everyone on your mesh.

**Add one:** long-press the map. Give it a name, and optionally a description and an icon.

| Option | What it does |
|---|---|
| **Expires** | Removes the waypoint at a set time |
| **Local Only** | Saves it on this device only. Nothing is sent over the mesh. |
| **Locked** | Only you can edit it |

Shared waypoints go out on your primary channel. Anyone on that channel can see them. Pangea notifies you when someone else shares a new waypoint.

**Edit or delete:** tap the waypoint, then **Edit**. When deleting, choose **Remove from this device** or **Delete for everyone**.

## Geofences

A geofence turns a waypoint into a watched area. Pangea notifies you when a radio's reported location moves in or out of it.

Open a waypoint, tap **Edit**, and go to **Geofence**:

| Control | What it does |
|---|---|
| **Radius** | A circle around the waypoint, from 0.1 to 10 miles. **Off** for none. |
| **Set Bounding Box** | Draw a rectangle on the map instead, or as well |
| **Notify on Enter** | Notify when a radio moves in |
| **Notify on Exit** | Notify when a radio leaves |
| **Favorites Only** | Only notify for radios you've starred |

Geofence alerts are worked out on your device from the locations your radio hears. They aren't live tracking. Nothing about the geofence is sent over the mesh.

## Coverage estimate

**Estimate Coverage** shows roughly how far a radio at a given spot can reach, based on the terrain. It needs an internet connection.

Open it from the signal-bars map button, or from a radio's details under **Logs → Estimate Coverage**.

| Section | What to set |
|---|---|
| **Site / Transmitter** | Location, power, frequency, antenna height and gain. Fill the location from your location, a node, or the map center. |
| **Receiver** | How weak a signal the other radio can still hear |
| **Simulation Options** | Maximum range, and **High-resolution terrain** (more detail, but caps range at 70 km) |
| **Display** | The color palette |

Pangea fills in the frequency, power and receiver from your radio's settings. Antenna height and gain aren't stored on the radio, so check those yourself.

Tap **Estimate**. The result is added to the map as an overlay marked **Site Planner**. Only the newest one stays on.

## Trace routes on the map

A trace route shows the path a message takes through the mesh. To run one, open a radio in the **Nodes** tab and tap **Trace Route**. Past results are under **Settings → Logging → Trace Routes**.

Open a result and tap **Show on Map**:

| What you see | Meaning |
|---|---|
| Solid line | The path out to the other radio |
| Dashed line | The path back |
| Green, yellow, orange, red | Good, fair, bad, or no signal on each hop. See [Signal Meter](signal-meter.md). |
| Green marker | Where the trace started |
| Red marker | The radio you traced |

Tap **▶** for a 3D flyover of the route. Tap the speed button to go from 1× to 5×, and **■** to stop.
