# Dataset

Phone: iPhone 13 Pro Max (iOS), app: Sensor Logger v1.68, sampling rate: 100 Hz (10 ms) for both sensors.
Phone held flat, screen up, at waist level (still: flat on a surface).

## Layout
- `train/<activity>/<activity>_NN.csv`: one merged file per recording (13 per activity, 52 total). This is what the notebook reads.
- `raw/<activity>/<activity>_NN/`: the original Sensor Logger `Accelerometer.csv`, `Gyroscope.csv` and `Metadata.csv` for each recording.
- `test/`: the 2 unseen test recordings (chained activities + `labels.txt`).
- `recordings_index.csv`: one row per recording (date, start time, device, sampling rate, samples, duration, max gap).

## Columns (train CSVs)
| column | unit | meaning |
|---|---|---|
| timestamp_ns | ns (Unix epoch) | sample timestamp |
| seconds_elapsed | s | time since the first sample of the recording |
| acc_x, acc_y, acc_z | m/s² | user acceleration (gravity removed) |
| gyro_x, gyro_y, gyro_z | rad/s | angular velocity |
| activity | – | still / standing / walking / jumping |

Accelerometer and gyroscope samples were aligned by nearest timestamp (≤ 5 ms tolerance; all samples matched).
The first and last 1 s of each recording (the start/stop tap) are trimmed in the notebook, not in these files.

## Sessions
| Files | Date | Location |
|---|---|---|
| `*_01`-`*_04` (Session A, filmed: `*_01` of each activity) | 2026-10-23 | Outdoor, university campus, pavement, Ancona |
| `walking_05`-`_13` (Session B) | 2026-10-25 | Outdoor, Globo Ancona, pavement, Ancona |
| `still_05`-`_13`, `standing_05`-`_13` (Session B) | 2026-10-25 | Indoor corridor, ceramic floor, Ancona |
| `jumping_05`-`_13` (Session B) | 2026-10-26 | Building courtyard, concrete, Ancona |
| `test/test_01`, `test/test_02` | 2026-10-26 | Unseen test recordings (see test/README.txt) |
