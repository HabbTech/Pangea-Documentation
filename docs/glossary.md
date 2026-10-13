# Glossary

| Term | Meaning |
|---|---|
| **LoRa** | "Long Range." A low-power radio signal that carries small amounts of data a long way. |
| **Mesh** | A network where every radio can pass messages along for others, with no central tower. |
| **Radio / node** | A LoRa device running Meshtastic firmware. Each one has its own ID. |
| **Hop** | One radio passing a message to the next. Pangea allows 3 hops by default. |
| **Relay** | A radio that repeats a message it heard so it travels farther. |
| **Channel** | A shared key and name radios use to talk. Everyone Nearby and each group are channels. |
| **Everyone Nearby** | The public default channel. Anyone in range can read it. |
| **Group** | A private channel with its own key, shared by invite. |
| **Code** | Your personal `@XXXX-XXXX` handle, made from your radio's ID. |
| **Node ID** | A radio's ID in Meshtastic format, like `!a1b2c3d4`. |
| **PKC** | Public-key cryptography. How private messages are encrypted between two radios. |
| **Region** | The legal frequency band for your country, like US 915 MHz or EU 868 MHz. |
| **Pairing code** | The Bluetooth PIN your phone asks for the first time it connects to a radio. |
| **Firmware** | The software running on the radio. Pangea needs Meshtastic 2.5.18 or newer. |
| **Expert Mode** | A setting that shows the full radio configuration. |
| **Airtime** | Time a radio spends transmitting. LoRa is slow, so Pangea keeps background traffic small. |
| **SNR / RSSI** | Signal quality and strength. Higher is better. Around −20 dB SNR is the edge of reception. |
