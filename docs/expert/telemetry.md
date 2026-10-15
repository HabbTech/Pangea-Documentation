# Telemetry & Sensors

Radios send small reports about themselves, like battery level and how busy the channel is. Radios with sensors attached can also send temperature, air quality and more. This is called telemetry.

- [Where to see it](#where-to-see-it)
- [Types of telemetry](#types-of-telemetry)
- [Telemetry settings](#telemetry-settings)
- [Detection Sensor](#detection-sensor)
- [Keep the airtime down](#keep-the-airtime-down)

## Where to see it

- **Node details.** Open a node in the **Nodes** tab. The latest readings show in the **Environment**, **Air Quality** and **Power** sections.
- **Logs.** Under **Logs** in node details, each type has its own log with a chart and a table. Tap **Save** to export one as CSV, or **Clear Log** to delete it from this device.

See [Nodes](nodes.md#logs-and-charts) for the full list of logs.

Readings follow your device's units, like °F or °C. See [Units & Language](units-and-locale.md).

## Types of telemetry

| Type | What's in it | Needs a sensor |
|---|---|---|
| **Device metrics** | Battery level, voltage, channel use, airtime | No |
| **Local stats** | Packets sent, received, relayed, duplicated and dropped, nodes online, and the noise floor | No |
| **Environment** | Temperature, humidity, pressure, and on some sensors wind, rain and radiation | Yes |
| **Air quality** | PM1.0, PM2.5 and PM10 particles, in µg/m³ | Yes |
| **Power** | Voltage and current | Yes |

A few terms:

- **Channel use** is how much of the time the radio heard someone transmitting. The higher it is, the more crowded the mesh.
- **Airtime** is how much of the time this radio spent transmitting itself.
- **Noise floor** is the background radio noise, in dBm. Lower (more negative) is quieter. It changes quickly, so look at the trend, not one reading.

Common sensors include the BME280 and BME680 (temperature, humidity, pressure), SHT31, MCP9808, INA219 and INA260 (power), and PMSA003 (air quality). Which ones work depends on the radio. Check with the radio's maker.

## Telemetry settings

**Settings → Telemetry** (shows **Expert Mode** under the name)

These settings are for the radio you're connected to.

| Section | Setting | What it does |
|---|---|---|
| Device Options | **Broadcast Device Metrics** | Sends battery and channel reports to the mesh, plus how often |
| Environment Sensor Options | **Environment Metrics Enabled** | Reads and sends an attached environment sensor, plus how often |
| | **Show on device screen** | Shows readings on the radio's screen |
| | **Display Fahrenheit** | Uses °F on the radio's screen. Pangea uses your device's setting either way. |
| Air Quality Sensor Options | **Air Quality Metrics Enabled** | Reads and sends an attached air quality sensor, plus how often |
| Power Sensor Options | **Power Measurement Enabled** | Reads and sends an attached power sensor, plus how often |
| | **Power Screen** | Shows power readings on the radio's screen |

Tap **Save** to send the changes to the radio.

## Detection Sensor

**Settings → Detection Sensor** (shows **Expert Mode** under the name)

The Detection Sensor sends an alert when a motion sensor or door switch wired to the radio is triggered. Alerts show up as messages and in the node's **Detection Sensor Log**.

| Setting | What it does |
|---|---|
| **Detection Sensor Enabled** | Turns it on. Turn it on both on the radio with the sensor and on radios that should get the alerts. |
| **Name** | The name used in the alert message |
| Minimum time between broadcasts | Stops a busy sensor from flooding the mesh |
| **State Broadcast Interval** | How often to send the sensor's state, even when nothing happened |
| **Send Bell** | Adds a bell to the alert, which can set off a buzzer on other radios |

## Keep the airtime down

Every report uses airtime that messages could have used.

- Leave intervals long. Every 30 minutes or more is plenty for most uses.
- Turn off sensors you don't use.
- In regions with a duty cycle limit, like EU_868, the radio stops sending once it hits its hourly limit. That includes your messages. Pangea shows **Hourly Duty Cycle** at the top of **Radio Configuration** when this applies.
