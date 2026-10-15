# TAK

**Settings → TAK Server** (shows **Expert Mode** under the name)

TAK (Team Awareness Kit) apps like iTAK and ATAK show team members, markers and routes on a shared map. Pangea can run a small TAK server on your device, so a TAK app on the same phone or tablet can send and receive over your radio. No cell service or internet needed.

- [What you need](#what-you-need)
- [Set up your channel](#set-up-your-channel)
- [Turn on the server](#turn-on-the-server)
- [Connect your TAK app](#connect-your-tak-app)
- [TAK Identity](#tak-identity)
- [Receiving routes](#receiving-routes)
- [Troubleshooting](#troubleshooting)

## What you need

- A TAK app, like iTAK, on the same device as Pangea.
- Radio firmware 2.3 or newer. Firmware 2.8.0 or newer adds shapes, markers, routes and emergency alerts. Older firmware sends positions and chat only. Pangea picks the right format for you.
- For best results, set your radio's role to **TAK** or **TAK Tracker** under **Settings → Device**.

## Set up your channel

TAK needs a private primary channel. On the public default channel, the server runs in **Read-Only Mode**: your TAK app can see the mesh, but can't send to it.

If your channel isn't suitable, you'll see a **Warning** at the top of the screen. To fix it:

- Tap **Auto-Fix Channel**, then **Fix Channel**. Pangea sets your primary channel to the name **TAK**, a new 256-bit key, and the **Short Range - Fast** preset. Or:
- Set a channel name and a 256-bit key yourself under **Settings → Channels**.

> [!WARNING]
> Changing your primary channel takes your radio off **Everyone Nearby** and anything else on the old channel. Old channel QR codes and links stop working. Everyone on your TAK team needs the new channel. After the fix, Pangea offers **Share with TAK Buddies**, or use **Settings → Share QR Code**.

## Turn on the server

Under **Configuration**:

| Setting | What it does |
|---|---|
| **Enable TAK Server** | Starts the server |
| Port, Security | Fixed at 8089, with mutual TLS. Both sides need certificates. |
| **Read-Only Mode** | Lets TAK see the mesh, but blocks TAK from sending to it |
| **Mesh to CoT Converter** | Shows Pangea positions, nodes, waypoints and messages in your TAK app |
| **TAK Channel Index** | The channel TAK messages are sent on |
| **Restart Server** | Restarts it after a change |

**Server Status** shows whether it's running, and warns if your device role isn't **TAK** or **TAK Tracker**.

## Connect your TAK app

1. Under **Client Configuration**, tap **Download TAK Server Data Package**. Pangea makes a `.zip` file.
2. Share or save it, and open it in your TAK app. It tells the app where the server is and which certificates to trust.

**TLS Certificates** comes with a built-in certificate that works for apps on the same device. To use your own, tap **Import Custom .p12** and enter its password. **Reset to Default** or **Reload Bundled Certificates** puts the built-in ones back. Certificates are kept in the device keychain.

## TAK Identity

**TAK Identity** sets how your radio shows up in TAK apps. It only applies when your role is **TAK** or **TAK Tracker**, and needs firmware 2.8.0 or newer.

| Setting | Options |
|---|---|
| **Team** | A team color. Cyan by default. |
| **Role** | Team Member (the default), Team Lead, HQ, Sniper, Medic, Forward Observer, RTO or K9 |

Tap **Save TAK Identity**. TAK apps see the change with your next position report.

If the pickers are greyed out, Pangea is still loading the settings from your radio. Give it a few seconds, or reconnect.

## Receiving routes

iTAK ignores routes that arrive over its live connection. So when someone sends a route over the mesh, Pangea saves it as a file and notifies you: **Route Received**.

To open it:

1. Open the Files app and go to **On My iPhone → Pangea → TAK Routes**.
2. Share the `.zip` to iTAK and choose **Import Mission Package**.

The **TAK Routes** folder appears the first time a route arrives.

## Troubleshooting

**My TAK app won't connect**
- Check **Enable TAK Server** is on.
- Open the data package in your TAK app again.
- If you imported your own certificate, check it's the one your app trusts.

**My TAK app can see the mesh but can't send**
The server is in **Read-Only Mode**. Fix your primary channel first. If the channel is already private, turn **Read-Only Mode** off.

**Team and Role don't show up**
Your radio's role needs to be **TAK** or **TAK Tracker**.
