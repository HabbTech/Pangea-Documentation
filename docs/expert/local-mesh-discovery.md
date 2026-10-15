# Local Mesh Discovery

**Settings → Local Mesh Discovery**

Local Mesh Discovery finds out which radio settings people near you are using. It tunes your radio to one LoRa preset after another, listens on each, and shows you which ones are busiest.

Use it when you arrive somewhere new and want to join the local mesh, or to check how crowded your current setting is.

- [Two ways to scan](#two-ways-to-scan)
- [Running a full scan](#running-a-full-scan)
- [Reading the results](#reading-the-results)
- [Beacons](#beacons)
- [Past scans and PDF reports](#past-scans-and-pdf-reports)

## Two ways to scan

| Option | What it does | How long |
|---|---|---|
| **Start Scan** | Listens on each preset you pick, one after another | The listening time you choose, for each preset |
| **Analyze Current Preset** | Reports on the preset you're already using, from everything Pangea has already heard. No settings change and no restart. | About a minute |

**Analyze Current Preset** works even with no radio connected.

## Running a full scan

1. Open **Settings → Local Mesh Discovery**.
2. Pick the presets to scan. A star marks the presets most public meshes use. A beacon icon marks presets a beacon has advertised. Both are picked for you.
3. Choose a **Dwell Duration**: how long to listen on each preset, from 15 to 180 minutes.
4. Tap **Start Scan**.

Keep Pangea open and the radio connected until it finishes. You can tap **Stop Scan** at any time.

> [!NOTE]
> The radio restarts each time the scan moves to a new preset. While it scans, your radio is off your usual mesh, so you won't get messages there. When the scan ends or you stop it, Pangea puts your preset, frequency slot and primary channel back the way they were.

## Reading the results

When the scan finishes, tap **View Summary**.

| Section | What it shows |
|---|---|
| **Session Overview** | How many nodes were found and how many messages and sensor reports were heard |
| **Per-Preset Results** | For each preset: nodes heard, channel use, airtime and noise |
| **RF Health** | The noise floor on each preset. Lower (more negative) means a quieter, cleaner channel. Only shown when your radio reports it. |
| **Recommendation** | The preset with the most nodes, the least crowded one, and the quietest one |
| **Discovery Map** | Where the nodes it heard are, if they shared a location |

On devices with Apple Intelligence, Pangea also writes a short recommendation on the device. Nothing is sent to the internet. Tap **Re-run Analysis** to write it again.

| Term | Meaning |
|---|---|
| **Direct** | Nodes heard with no hops in between |
| **Infrastructure** | Routers and repeaters |
| **Ch Util** | How much of the time the channel was busy |
| **Noise** | Background radio noise in dBm |

## Beacons

Some radios send a short beacon that advertises their mesh: a message, and sometimes the channel, region and preset they use. Beacons Pangea hears show up under **Beacons** in the results, and under **Nearby Meshes**.

- A beacon for the public channel adds its preset to the scan, and pre-selects it next time.
- A beacon for a private channel includes the channel's name and key, so the scan can tune to it and measure that mesh too.

Each beacon has buttons to join its mesh:

| Button | What it does |
|---|---|
| **Add channel** | Adds the advertised channel as an extra channel. Your radio stays on its current mesh, with no restart. Only offered when the mesh is on the same frequency your radio already uses. |
| **Switch to this channel** | Makes the advertised channel your primary channel and applies its region and preset. The radio restarts and joins that mesh. Your old channel settings are replaced. |

If all your secondary channel slots are full, Pangea asks which one to replace. Your primary channel is never touched by **Add channel**.

> [!WARNING]
> Adding a channel uses up one of your 8 channel slots, the same ones Pangea uses for groups. See [Limits](../limits.md).

## Past scans and PDF reports

Earlier scans are kept under **Session History**. Swipe left to delete one.

From a scan summary, tap the share button to save it as a PDF.
