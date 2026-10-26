Unseen test recordings (never used for training or for fitting the feature scaler).

test_01  still -> standing -> walking -> jumping  (recorded 2026-10-26 13:37, 48.0 s)  source: still-stand-walk-jump-2026-10-26_13-37-01.zip
test_02  walking -> standing -> jumping -> still  (recorded 2026-10-26 13:35, 51.0 s)  source: walk-stand-jump-still-2026-10-26_13-35-11.zip

labels.txt: start_s,end_s,activity (seconds since the recording started).
The activity order is the script I followed while recording. The switch times were marked by inspecting the
raw accelerometer/gyroscope plots, where each change is visible as a step in signal intensity.
Seconds not covered by any segment (test_01 12.9-14.3 s: picking the phone up from the table;
test_02 38.2-39.0 s: putting it down) are handling transitions and are excluded from scoring.
