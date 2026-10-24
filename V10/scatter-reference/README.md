# Multilaser M8 4G — V10 partition references

Firmware: V10_20250807 (Android 13) · SoC: MT6765/MT8768t · device: ML_SO0V_M8_4G.

- `MT6765_Android_scatter_V10_REFERENCE_ONLY.txt`: scatter-format partition map derived from the V10 GPT. This is a **reference only**, NOT validated for SP Flash Tool, and all entries are intentionally marked `is_download: false`.
- `partition_layout_V10.csv`: 49 GPT-defined partition names, offsets, lengths and LBAs, independently useful for documentation/comparison.

The eMMC boot region/preloader is not covered by this GPT. No raw preloader, GPT binaries, unique partition GUIDs, hardware identifiers, or private device data are included. **Do not use this package to flash, format, or restore a tablet.** Verify hardware and firmware compatibility before any recovery operation.
