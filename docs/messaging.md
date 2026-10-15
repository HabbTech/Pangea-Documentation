# Messaging

- [Chat types](#chat-types)
- [Personal codes](#personal-codes)
- [Private messages](#private-messages)
- [Groups](#groups)
- [Everyone Nearby](#everyone-nearby)
- [Mentions](#mentions)
- [Delivery status](#delivery-status)
- [Deleting and leaving chats](#deleting-and-leaving-chats)
- [Notifications](#notifications)
- [Messages in Expert Mode](#messages-in-expert-mode)

## Chat types

| Type | Who can read it | Encryption | Limit |
|---|---|---|---|
| **Private message** | You and one other person | End-to-end, between your two radios | None |
| **Group** | People you invite | A private key shared only through the invite | 7 groups per radio |
| **Everyone Nearby** | Every radio in range on default settings | Public default key. Treat it as public. | One, always there |

The Chats list shows **Everyone Nearby** first, then your groups and private messages, newest first.

## Personal codes

Every Pangea user has a code made from their radio's ID:

```
@4KQ2-F9MX
```

- 8 characters, with the last one a check character, so most typos are caught before anything is sent.
- Letters that look alike are left out (no `I`, `L`, `O` or `U`). Case doesn't matter, and the `@` and dash are optional.
- Your code belongs to your **radio**. If you switch to a different radio, you get a different code.

Ways to share it:

| Method | Works from far away | Swaps keys instantly |
|---|---|---|
| QR code (**Show QR**) | No, scan in person | Yes |
| Share link (`pangea://dm/…`) | Yes | Yes |
| Typing the code | Yes | No, needs the other radio in range |

Pangea also accepts Meshtastic node IDs like `!a1b2c3d4` and Meshtastic contact links.

## Private messages

Private messages are encrypted end to end between the two radios. Radios that relay the message along the way can't read it.

Before the first message, both radios need each other's public key:

- **Scanning a QR code or opening a link** includes the key, so you can message right away.
- **Typing a code** makes Pangea say hello over the mesh. When the other radio answers, the keys are swapped and the chat opens. If it can't be reached, you'll see **Couldn't reach … yet** with a **Try Again** button.

Pangea won't send a private message until it has the other person's key, so a private message never goes out on the public channel by mistake.

## Groups

A group is a private channel with its own random 256-bit key.

**Create:** Compose button → **New Group** → enter a name (up to 11 characters).

**Invite** from the group's menu → **Invite People**:

| Option | How |
|---|---|
| QR code | They scan it in Pangea |
| Share link | Send `pangea://group#…` any way you like |
| Contacts | Tap **Invite** next to a saved contact or someone you've messaged |
| Code | Type their `@code` or scan their QR code under **Invite by Code** |

Invites sent from inside the app travel as an encrypted private message, so only that person can join.

**Join:** open the link, scan the QR code, or accept the invite when it shows up at the top of Chats.

**Limit:** a radio holds 8 channels. One is Everyone Nearby, so you can be in up to **7 groups** at once. If you're full, Pangea asks you to leave one to make room.

## Everyone Nearby

Everyone Nearby is the public mesh channel that every radio on default settings shares. Use it to say hello to whoever is around.

- Anyone in range can read it, including people on other Meshtastic apps.
- Your profile photo and emoji are **never** sent here.
- Notifications are **off** by default. Tap the bell in the chat to turn them on.
- It can't be deleted or left.

## Mentions

Type `@` in a group and pick a name to mention someone. Mentions show as links to that person's profile, for you and for other Pangea users in the group.

## Delivery status

| Status | Meaning |
|---|---|
| **Sending…** | Your radio has the message and is trying to send it. |
| **Delivered** | The other person's radio confirmed it. (Private messages) |
| **Sent** | Another radio picked it up and passed it on. (Groups and Everyone Nearby) |
| **Sent. They haven't confirmed it yet.** | A relay took it, but the person's radio hasn't confirmed it yet. |
| **Not delivered. They may be out of range.** | Nobody confirmed it after several tries. Tap **Try Again**. |
| **Your radio couldn't send this.** | The message never reached your radio, usually because Bluetooth dropped. |

A message that gets no answer at all moves from **Sending…** to **Not delivered** after about 5 minutes. If a late confirmation arrives, the status updates on its own. Pangea never resends a message unless you tap **Try Again**.

Messages can be up to **200 bytes**. That's about 200 letters, or fewer with emoji.

## Deleting and leaving chats

| | iPhone / iPad | Mac |
|---|---|---|
| Delete a private chat | Swipe left → **Delete Chat** | Right-click → **Delete Chat** |
| Leave a group | Swipe left → **Leave Group** | Right-click → **Leave Group** |

- **Delete Chat** removes that conversation's messages from this device only. The other person keeps their copy, and the contact, nickname and profile stay.
- **Leave Group** removes the group from your radio and deletes its messages on this device. You'll need a new invite to rejoin.
- Both ask before doing anything. Leaving a group needs your radio connected.
- Everyone Nearby, and chats with your own radios, can't be deleted.

## Notifications

| Chat | Default |
|---|---|
| Private messages | On |
| Groups | On |
| Everyone Nearby | Off. Turn on with the bell in the chat. |
| Group invites | On |

Notifications are cleared when you delete the chat or leave the group they belong to.

## Messages in Expert Mode

With [Expert Mode](settings.md#expert-mode) on, **Chats** becomes **Messages**. Your conversations are the same, but they're sorted by how they travel over the radio:

| List | What's in it |
|---|---|
| **Channels** | Everyone Nearby and your groups, listed as the radio's channels |
| **Direct Messages** | Your private chats, and anyone else your radio can message |

Extra things you can do in a conversation:

| Action | How |
|---|---|
| Search | Type in **Find in conversation** at the top. It searches the whole history. |
| React | Long-press a message → **Tapback** |
| Reply | Long-press a message → **Reply** |
| Copy or delete | Long-press a message → **Copy** or **Delete** |
| See signal details | Long-press a message. The menu shows when it was sent, the SNR and RSSI, how many hops away the sender is, how many radios relayed it, and when it was confirmed. |
| Load older messages | Scroll to the top and tap **Load Earlier Messages** |

Long-press a channel message to check where it came from. If the sender's radio signed it and your radio checked the signature (firmware 2.8 or newer), the menu shows **Signed · verified**. Unsigned messages aren't a problem. Private messages and messages from older radios are never signed.

Delivery status uses the radio's own wording in Expert Mode. For example, **Not delivered** shows as **Max Retransmission Reached**. **Try Again** works the same way.

Channel settings, like a channel's name, key and MQTT options, are under **Settings → Channels**. See the [Expert Mode guides](expert/README.md).
