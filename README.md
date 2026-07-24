# Meta-360 Dataset

This dataset contains synchronized application-level and network-level measurements collected while streaming immersive **360° YouTube videos over a commercial 5G network**.

The 360° videos were played on a **Meta Quest 3** headset connected through Wi-Fi to a **Samsung Galaxy S25+ 5G hotspot**. Application-level video information was collected from the YouTube player, while cellular radio and network measurements were recorded on the smartphone.

Each row represents an approximately one-second measurement. The `Eid_num` column identifies the experimental session to which the measurement belongs.

## Dataset Columns

| Column | Description |
|---|---|
| `Video` | YouTube video identifier of the streamed 360° video. |
| `Quality` | Playback quality reported by the YouTube player. Observed values include `large`, `hd720`, `hd1080`, `hd1440`, and `hd2160`. |
| `Video Bytes Downloaded` | Fraction of the video loaded by the YouTube player, represented as a value between 0 and 1. Despite the column name, this field does not represent the actual number of downloaded bytes. |
| `Loaded Percentage` | Percentage of the video loaded by the YouTube player. It is approximately equal to `Video Bytes Downloaded × 100`. |
| `Longitude` | Longitude of the smartphone location during the measurement, represented in decimal degrees. |
| `Latitude` | Latitude of the smartphone location during the measurement, represented in decimal degrees. |
| `RSRP` | Serving-cell Reference Signal Received Power, measured in dBm. It represents the strength of the received cellular reference signal. Less-negative values generally indicate stronger signal power. |
| `RSRQ` | Serving-cell Reference Signal Received Quality, measured in dB. It represents the quality of the received cellular signal. Less-negative values generally indicate better signal quality. |
| `SNR` | Serving-cell Signal-to-Noise Ratio, measured in dB. Higher values generally indicate better signal conditions. |
| `DL_bitrate` | Downlink bitrate reported by the smartphone during the measurement, measured in kbps. |
| `UL_bitrate` | Uplink bitrate reported by the smartphone during the measurement, measured in kbps. |
| `State` | Network activity state reported by the measurement application. `I` represents idle, `D` represents active data transmission, and `VD` represents simultaneous voice and data activity. |
| `EVENT` | Cellular-network event recorded during the measurement. Examples include periodic measurements, handovers, cell reselections, and inter-radio-access-technology events. |
| `SecondCell_RSRP` | Reference Signal Received Power of the secondary cell or LTE anchor cell, measured in dBm. |
| `SecondCell_RSRQ` | Reference Signal Received Quality of the secondary cell or LTE anchor cell, measured in dB. |
| `SecondCell_SNR` | Signal-to-Noise Ratio of the secondary cell or LTE anchor cell, measured in dB. |
| `Eid_num` | Unique identifier of an experimental streaming session. Rows with the same `Eid_num` belong to the same experiment. |

## Notes

- Measurements were recorded at approximately one-second intervals.
- The original row order represents the temporal order of measurements within each experiment.
- The dataset does not contain an explicit timestamp column.
- Temporal and rolling-window features should be calculated separately for each `Eid_num`.
- Missing secondary-cell values indicate that secondary-cell information was not reported for that measurement.
- `EVENT` represents a cellular-network event and should not be interpreted as a video QoE-degradation label.


## Videos Used for Dataset Collection

The following 360° YouTube videos were used for dataset collection.

| # | YouTube ID | Title on YouTube | Video Category | Total Length |
|---|---|---|---|---|
| 1 | `nV_hd6bLXmw` | SLIDE in 360° \| VR / 4K | Amusement / VR Ride | 1:14 |
| 2 | `nF8UTFHpmjE` | Wild Cats in the Primorsky Safari Park, Vladivostok, Russia. 360 video in 16K | Wildlife / Nature | 6:40 |
| 3 | `KGerjHMa90s` | London, United Kingdom. Virtual travel. 360 video in 8K | Travel / City Tour | 6:13 |
| 4 | `idCX7o-9Hr4` | Rosa Khutor Ski Resort. Southern slope. Sochi, Russia. 360 video in 4K | Travel / Winter Sports | 5:16 |
| 5 | `dwHBpykTloY` | First-Ever 3D VR Filmed in Space \| One Strange Rock | Science / Space Documentary | 4:33 |
| 6 | `G-XZhKqQAHU` | 360 Google Spotlight Stories: HELP | Animated Short / Sci-Fi | 2:03 |
| 7 | `DhE9J_XbeK4` | Bosch Automated Driving VR Experience | Automotive / Technology | 3:28 |
| 8 | `Z-ihuDLNVR8` | [360°/VR Video] Méditation & Relaxation | Relaxation / Meditation | 3:00 |
| 9 | `jMB7-v50hck` | 360 video Boxing VR Rocky Balboa's Creed Rise to Glory vs Mexican in Mexico Win Oculus Rift S | Sports / Boxing / Gameplay | 4:25 |
| 10 | `D6FRezJF3rU` | Admiring the Beauty of Kaaba up Close - Makkah \| 360° Video | Religion / Pilgrimage | 4:54 |
| 11 | `A6aRkhlqWuE` | The Conjuring 2 - Experience Enfield VR 360 [HD] | Horror / Entertainment | 3:09 |
| 12 | `LJyclVpwAio` | VR 360° MINIONS PRISON BREAK | Animation / Comedy | 2:55 |
| 13 | `Zgaw2eNP9eo` | Experience the Elusive Tiger \| Racing Extinction (360 Video) | Wildlife / Conservation | 3:37 |
| 14 | `HI7mTIxNotQ` | Elephant Encounter in 360 - Ep. 2 \| The Okavango Experience | Wildlife / Documentary | 6:14 |
