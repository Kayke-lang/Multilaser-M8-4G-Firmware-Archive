# Multilaser M8 4G Firmware Archive

Unofficial community-maintained firmware archive for the Multilaser M8 4G tablet.
This repository indexes firmware downloads, checksums, and experimental recovery documentation.

## Device Information

```text
Manufacturer:       Multilaser
Model:              M8 4G
Device:             M8_4G
Firmware variant:   SO0V
Platform:           MediaTek MT6765
Architecture:       ARM64
```

Compatibility is not guaranteed across hardware revisions or other variants (including SO1V).
Always verify the exact model and partition layout before attempting recovery.

## Available Firmware

### GOV V3

```text
Version:            GOV V3
Package:            Multilaser_M8_4G_GOV_V3_Public_Recovery_Dump.tar.zst
Format:             Unofficial MTKClient dump, repackaged for public review
Flash status:       Full restoration NOT tested
Download:           Coming soon
```

- Contains 30 selected firmware images.
- Includes `README.md`, `FLASHING_GUIDE.txt`, and `SHA256SUMS`.
- Known sensitive partitions were excluded from the public package.
- The original full-device archive is private and should not be published.
- The GPT from the original V3 backup was not included because it has not been independently validated.

### Stock V10

```text
Version:            V10.20250807
Format:             Existing stock ROM archive (ZIP)
Flash status:       Previously flashed successfully on tested M8 4G hardware
Download:           [SourceForge — Stock V10](https://sourceforge.net/projects/multilaser-m8-4g-so0v-rom/files/Dump_Multilaser_M8_4G_SO0V_Stock-ROM_V10.20250807.zip/download)
```

The V10 archive is hosted by a separate SourceForge project. Its contents and distribution terms are not controlled by this repository.

### GOV V14 (Partial)

```text
Version:            GOV.V14_20251220
Availability:       Selected slot-A components inside the V15 dump
Flash status:       NOT a complete standalone ROM
Download:           Included in GOV V15 archive (when published)
```

Do not attempt to restore GOV V14 using only these partial components.

### GOV V15

```text
Version:            GOV.V15_20260310
Package:            Multilaser_M8_4G_GOV_V15_Recovery_Dump.tar.zst
Format:             Unofficial MTKClient firmware dump
Flash status:       Full restoration NOT tested
Download:           Coming soon
```

- Slot A contains GOV V14 boot and AVB components.
- Slot B contains GOV V15 boot and AVB components.
- `super.bin` contains Virtual A/B metadata and COW partitions.
- The available backup has not been demonstrated to recreate a fully bootable V15 installation.

## Download Verification

Check the downloaded archive against its separately published `.sha256` file:

```sh
sha256sum -c FILENAME.tar.zst.sha256
```

Replace `FILENAME` with the actual archive filename, and run the command in the directory containing both files.

After extracting a firmware archive, verify the included images:

```sh
sha256sum -c SHA256SUMS
```

A valid checksum confirms that the file matches the recorded digest; it does **not** prove that the firmware is compatible, safe to flash, or free of device-specific information.

## Recovery and Flashing

Read the guide included with each package **before** attempting any flash operation.

**WARNING:** The GOV V3 and GOV V15 packages are experimental firmware dumps, **not validated one-click recovery ROMs**. Do not treat the included images as a verified set of flashing commands.

- Back up your target device before making changes.
- Confirm the exact tablet model, hardware revision, bootloader state, and partition layout.
- Never blindly flash the preloader or GPT.
- Preserve device-specific partitions such as NVRAM, NVDATA, and calibration data.
- Do not mix images from different slots or firmware generations without validation.
- Do not relock the bootloader with experimental firmware.
- Keep a known-working recovery route available.

## Privacy and Redistribution

The original GOV V3 backup includes partitions that may contain unique identifiers, private data, and device-specific calibration. **Do not redistribute the original full backup.** The public V3 package excludes known sensitive partitions, but its selected firmware images still require review before publication.

The V15 archive likewise requires review for identifiers and distribution permissions before public release. Excluding obvious private partitions is not proof of anonymization.

This repository is unofficial and is not affiliated with Multilaser, MediaTek, or Google. Firmware copyrights remain with their respective owners. Hosting or linking a dump does not itself grant redistribution rights.

## Contributions

Firmware metadata, verified checksums, documentation improvements, and compatibility reports are welcome. Do not submit device-specific identity or security partitions, personal information, or unverified flashing instructions.

## Disclaimer

All files and information are provided as-is, without warranty. Firmware flashing can cause data loss, bootloops, or permanent device damage. Proceed only if you understand the risks.
