# Troubleshooting

Find your problem, try the fixes in order.

- [Messages say "Not delivered"](#messages-say-not-delivered)
- [I get messages but can't send any](#i-get-messages-but-cant-send-any)
- [My radio doesn't show up](#my-radio-doesnt-show-up)
- [It keeps asking for a pairing code](#it-keeps-asking-for-a-pairing-code)
- ["Peer removed pairing information"](#peer-removed-pairing-information)
- [Everyone Nearby or a group is missing](#everyone-nearby-or-a-group-is-missing)
- ["Couldn't reach … yet"](#couldnt-reach--yet)
- [A photo won't download](#a-photo-wont-download)
- [The map is empty](#the-map-is-empty)
- [Radios show up as "Meshtastic 1a2b"](#radios-show-up-as-meshtastic-1a2b)
- [Asking for help](#asking-for-help)

---

## Messages say "Not delivered"

Expert Mode shows this as **Max Retransmission Reached**.

**What it means:** your radio sent the message several times and nobody answered. The app and the message are fine. The radio signal didn't reach anyone.

**Fixes:**

1. **Check the antenna.** It should be screwed on firmly and on the right socket. On RAK4631 boards, use the socket marked **LoRa**.
2. **Get higher.** Move the radio to a window, a shelf, or outside. Height is the biggest single improvement.
3. **Test up close.** Put a second radio a few meters away and send to it. If that fails too, the radio itself may have a problem.
4. **Check the region.** Both radios need the same region. See [Regions](supported-hardware.md#regions).
5. Tap **Try Again** once you've moved.

## I get messages but can't send any

This is almost always the same problem as above. A strong radio on a rooftop or hill can reach you, but your radio isn't strong enough, or high enough, to reach back. Follow the [Not delivered](#messages-say-not-delivered) fixes, starting with the antenna.

## My radio doesn't show up

1. Make sure the radio is on and charged.
2. Turn Bluetooth on (**Settings → Bluetooth** on iPhone, Control Center on Mac).
3. Allow Pangea to use Bluetooth: iPhone **Settings → Pangea → Bluetooth**, or Mac **System Settings → Privacy & Security → Bluetooth**.
4. Close other Meshtastic apps. A radio only talks to one app at a time.
5. Restart the radio.

## It keeps asking for a pairing code

The code is only needed the first time. If it's asked for again:

- **Radio with a screen:** type the 6-digit number it shows.
- **Radio without a screen:** type `123456`.
- If **Expert Mode** is on, Pangea leaves the pairing setting as it is. Turn Expert Mode off and reconnect, or set the pairing mode yourself under **Bluetooth**.

## "Peer removed pairing information"

The radio forgot your phone, but your phone still remembers the radio. Clear it on the phone:

- **iPhone / iPad:** Settings → Bluetooth → tap ⓘ next to the radio → **Forget This Device**
- **Mac:** System Settings → Bluetooth → hover the radio → ⓘ → **Forget This Device**

Then connect again from Pangea.

## Everyone Nearby or a group is missing

1. Make sure **Expert Mode** is off. With it on, chats live in the **Messages** tab instead of **Chats**.
2. Connect your radio. The channel list comes from the radio, and fills in once it's connected.
3. Give it a few seconds after connecting. Groups appear as the radio sends its settings.

## "Couldn't reach … yet"

Pangea tried to swap keys with that person over the mesh and got no answer. Their radio may be off or out of range.

- Ask them for their **QR code** or **share link**. Those work instantly from any distance.
- Or tap **Try Again** when they're nearby.

## A photo won't download

- Photos download over the radio and take a few minutes. Keep the app open.
- Both radios need to be in range for the whole download.
- Only 6 photos download at once. Others wait their turn.
- If it says to connect your radio, reconnect and tap **Update Profile Photo** again.

## The map is empty

The map shows radios that have shared their location. Many radios don't have GPS or keep location off, so they never appear. Radios that do usually send their location every 15 to 30 minutes. The map is in the **Map** tab, which needs Expert Mode. See [Map & Waypoints](expert/map.md).

## Radios show up as "Meshtastic 1a2b"

That's a placeholder for a radio whose name hasn't arrived yet. The last four characters come from its ID. The real name replaces it as soon as the radio sends it.

## Asking for help

[Open an issue](../../../issues/new/choose) with:

- Your device (iPhone model or Mac) and OS version
- Pangea version (**Settings → About**)
- Radio model and firmware version
- What you did, what you expected, and what happened
