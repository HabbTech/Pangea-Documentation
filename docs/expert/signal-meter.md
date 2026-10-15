# Signal Meter

The signal bars on the **Nodes** tab, in node details, on the **Map** and in trace routes show how well your radio hears another one. They work differently from the bars on a phone.

- [Two measurements](#two-measurements)
- [Why negative numbers are normal](#why-negative-numbers-are-normal)
- [How the bars are worked out](#how-the-bars-are-worked-out)
- [What to look for](#what-to-look-for)

## Two measurements

Every time your radio hears a message, it measures two things:

| Measurement | What it is | Think of it as |
|---|---|---|
| **RSSI** | How strong the signal is at the antenna, in dBm | How loud someone's voice is |
| **SNR** | How far the signal stands out from background noise, in dB | How easy they are to understand in a noisy room |

A shout at a loud concert is loud but hard to understand. A whisper in a quiet library is faint but easy to follow. For LoRa, **SNR matters more than RSSI**.

## Why negative numbers are normal

Most radios can't hear a signal that's quieter than the background noise. LoRa can. It can pick a message out of the noise even when the signal is well below it. So an SNR like −10 dB is common and often fine.

How far below the noise a radio can still hear depends on the preset:

| Preset | Lowest usable SNR |
|---|---|
| Long Range - Slow | −20 dB |
| Long Range - Fast, Long Range - Moderate | −17.5 dB |
| Medium Range - Slow | −15 dB |
| Long Range - Turbo, Medium Range - Fast | −12.5 dB |
| Short Range - Slow | −10 dB |
| Short Range - Fast, Short Range - Turbo | −7.5 dB |

Your preset is shown on the **Connect** tab and under **Settings → LoRa**.

## How the bars are worked out

Pangea compares the SNR with the lowest usable SNR for your preset:

| Rating | Bars | Color | SNR compared with the preset's limit |
|---|---|---|---|
| **Good** | 3 | Green | Above the limit |
| **Fair** | 2 | Yellow | At the limit, down to 5.5 dB below it |
| **Bad** | 1 | Orange | 5.5 to 7.5 dB below the limit |
| **None** | 0 | Red | More than 7.5 dB below the limit |

If your radio has recently reported its **noise floor** (the background noise level), Pangea also works out the real gap between the signal and the noise, and shows whichever rating is worse.

If there's no noise floor reading, Pangea also checks RSSI against fixed levels (−115, −120 and −126 dBm) and shows whichever rating is worse.

The bars and the color of the SNR number always match.

## What to look for

**Low RSSI, good bars.** An RSSI like −118 dBm would be no bars on a phone. If SNR is +2 dB, the link is fine. It's a whisper in a quiet room.

**High RSSI, bad bars.** If RSSI is strong, like −90 dBm, but you only get one bar, something nearby is making noise. Common causes are cheap chargers, computers, LED lights and nearby transmitters. Move the radio away from them, or move the antenna.

The bars only rate nodes your radio hears directly. For nodes further away, a [trace route](nodes.md#trace-routes) shows the signal on each hop.
