# Logs & File Storage

Pangea keeps a log of what it's doing. If something goes wrong, the log helps us see why. Expert Mode lets you read it, filter it, and export it to send to us.

- [Opening the logs](#opening-the-logs)
- [Reading the logs](#reading-the-logs)
- [Filters](#filters)
- [Packet Stream](#packet-stream)
- [Exporting as CSV](#exporting-as-csv)
- [Sending logs to us](#sending-logs-to-us)
- [File Storage](#file-storage)

## Opening the logs

**Settings → Logging → Logs** (shows **Expert Mode** under the name)

The screen is called **Debug Logs**. The number next to the title is how many entries match your filters.

> [!IMPORTANT]
> The log only covers the time since Pangea was last opened. If you force-quit Pangea, or your device restarts, the earlier entries are gone from this screen. Export the log before you close the app.

## Reading the logs

| Device | What you see |
|---|---|
| iPhone | One line per entry, colored by level |
| iPad and Mac | A table with **Time**, **Level**, **Category** and **Message** |

Tap an entry to see all of it: the time, level, category and the full message.

Type in **Search** to find entries containing a word, like a node name or "error".

New entries don't appear on their own. Pull down to refresh (on Mac, tap the refresh button).

## Filters

Tap the filter button in the bottom-right corner to open **App Log Filters**.

**Categories** pick which part of Pangea the entries come from:

| Category | Covers |
|---|---|
| **Pangea** | Pairing and setup, chats and delivery, groups, contacts and profiles |
| **Admin** | Admin messages, like settings sent to and from radios |
| **Data** | Reading and saving data, including decoding errors |
| **Mesh** | Packets to and from the mesh |
| **MQTT** | The MQTT connection |
| **Radio** | Detailed logs sent by the radio itself |
| **Services** | Network requests, location and other system services |
| **Stats** | App statistics. Nothing here leaves your device. |
| **Transport** | The Bluetooth, Wi-Fi or USB connection |
| **TAK** | The TAK server |
| **Discovery** | Local Mesh Discovery scans |
| **Backup** | Saving and restoring each radio's node list |

**Log Levels** pick how serious the entries are: **Debug**, **Info**, **Notice**, **Error** and **Fault**. To see only problems, pick **Error** and **Fault**.

Pick none in a section to see everything. Tap **All** to select every item in a section.

## Packet Stream

**Packet Stream** shows mesh packets live as your radio sends and receives them. Turn it on at the top of **App Log Filters**. It ignores the category and level filters.

- The title changes to **Packet Stream**, with a count.
- New packets scroll in at the bottom. Scroll up to stop and read. Tap **Live** to jump back to the newest.
- Search still works.
- It shows up to the latest 1,000 packets.

To go back to the normal log, open the filters and turn **Packet Stream** off.

## Exporting as CSV

Tap the download button in the top-right corner. Pangea makes a CSV file named **Pangea Application Logs** with the date and time. Choose where to save it, like Files or your Desktop.

The export has the entries you're looking at, with your filters and search applied. In Packet Stream, it has every mesh packet since Pangea was opened, not only the ones on screen.

CSV files open in Numbers, Excel or any text editor.

## Sending logs to us

Logs are the fastest way for us to find a bug. Here's how to send them:

1. **Make it happen.** Open Pangea, then do whatever causes the problem. Don't close Pangea afterward.
2. **Open the logs.** Go to **Settings → Logging → Logs**.
3. **Clear the filters.** Make sure no categories, levels or search are set, so the export has everything.
4. **Export.** Tap the download button and save the CSV.
5. **Open an issue.** Go to [github.com/HabbTech/Pangea-Documentation/issues/new/choose](https://github.com/HabbTech/Pangea-Documentation/issues/new/choose) and attach the CSV.

In the issue, tell us:

- **What you did**, step by step, and what happened instead of what you expected.
- **When it happened**, with the time, so we can find it in the log.
- **Pangea version**, from **Settings → About Pangea**.
- **Radio model** and firmware version, from the **Connect** tab or **Settings → Firmware Updates**.
- Your device (iPhone, iPad or Mac model) and its OS version.

> [!WARNING]
> GitHub issues are public. Logs can include node names, node IDs and message details like who sent what and when. Open the CSV and look through it before you post. Remove anything you don't want to share.

Logs stay on your device. Nothing is sent anywhere until you export the file and share it yourself.

## File Storage

**Settings → Developers → App Files**

The **Developers** section shows in Expert Mode on test builds of Pangea, like the TestFlight version.

The screen is called **File Storage**. It lists the files Pangea keeps on this device.

| Section | What's in it |
|---|---|
| **Phone GPS** | Your device's current location, accuracy and heading |
| **Map Data** | Opens **Upload Map Data**, to manage map overlay files. See [Map Options](map.md#map-options). |
| **Active Database** | The size of Pangea's database: **Store**, **WAL**, **SHM**, and the **Total** |
| **Application Support** | Pangea's own files, including **Node Backup** files for each radio you've used |
| **Documents** | Files Pangea saved for you, like TAK routes |

To save a copy of a file, swipe left on it and tap **Download** (on Mac, use the download button on the row). To remove one, swipe left and tap **Delete**.

> [!WARNING]
> Delete happens right away, with no confirmation and no undo. Deleting a **Node Backup** means Pangea can't restore that radio's nodes and messages when you switch back to it. Only delete files if we've asked you to, or you know what they are.

Database and backup files can hold your messages, contacts and keys. Don't post them publicly. If we ask for one, we'll tell you how to send it privately.
