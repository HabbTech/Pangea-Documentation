# Limits

LoRa trades speed for range. These are the numbers to know.

| Item | Limit | Why |
|---|---|---|
| Message length | 200 bytes (about 200 letters, fewer with emoji) | Radio packet size |
| Private groups per radio | 7 | The radio holds 8 channels and one is Everyone Nearby |
| Group name | 11 bytes | Firmware channel name limit |
| Your name in Pangea | 64 bytes | Profile card size |
| Your name on the radio | 36 bytes long name, 4 bytes short name | Firmware limit |
| Profile photo | 256 × 256 px, about 14 KB | Sent in small pieces over LoRa |
| Photo download time | A few minutes | One piece every few seconds, to leave room for messages |
| Photo downloads at once | 6 | Keeps the channel free for chat |
| Profile update after an edit | Sent to 8 people right away, others when you next message them | Keeps airtime low |
| Hops | 3 by default | Each relay adds a hop. More hops means more airtime. |
| Time before "Not delivered" | About 5 minutes with no answer | The radio retries before giving up |
| Pasted code or link | 2 KB | Anything longer isn't a code |

## Typical range

| Setup | Rough range |
|---|---|
| Both radios in pockets, in town | 100 m to 1 km |
| One radio on a windowsill or vehicle roof | 1 to 5 km |
| Line of sight, hilltop to valley | 10 km and more |
| Rooftop or mountain relay in between | Much farther, through relays |

Range varies a lot with terrain, buildings, trees and antenna. See [Troubleshooting](troubleshooting.md#messages-say-not-delivered) if messages aren't getting through.
