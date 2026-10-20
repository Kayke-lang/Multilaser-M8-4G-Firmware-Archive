# Multilaser M8 4G Firmware Archive

Unofficial community-maintained firmware archive for the **Multilaser M8 4G (M8_4G / SO0V)** tablet.

This repository indexes firmware downloads, recovery information, and SHA-256 checksums. The files are provided for preservation and research; they are **not all validated flashable ROMs**.

## Device information

```text
Manufacturer:       Multilaser
Model:              M8 4G
Device:             M8_4G
Firmware variant:   SO0V
Platform:           MediaTek MT6765
Architecture:       ARM64
```

## Firmware downloads

### GOV V3

```text
Version:            GOV V3
Package:            Multilaser_M8_4G_GOV_V3_Public_Recovery_Dump.tar.zst
Status:             Unofficial public dump; full restoration untested
```

**Download mirrors**

- [MEGA](https://mega.nz/file/3b42yTgb#1nj6Jn-BvRV-nXmGctm4dMRTxkMLuYTir_KqQcSShZ0)
- [Internet Archive](https://archive.org/details/multilaser-m8-4g-gov-v3-firmware-dump)

**Verification**

- [SHA-256 checksum](checksums/Multilaser_M8_4G_GOV_V3_Public_Recovery_Dump.tar.zst.sha256)

This public archive includes selected firmware partitions and documentation. Known private partitions such as NVRAM, NVDATA, and PERSIST were excluded. The archive has not been validated for complete recovery; inclusion does not guarantee that every image is safe for public redistribution or flashing.

### Stock V10

```text
Version:            V10.20250807
Package:            Dump_Multilaser_M8_4G_SO0V_Stock-ROM_V10.20250807.zip
Status:             Existing stock firmware package
```

**Download**

- [SourceForge](https://sourceforge.net/projects/multilaser-m8-4g-so0v-rom/files/Dump_Multilaser_M8_4G_SO0V_Stock-ROM_V10.20250807.zip/download)

This stock V10 package has previously been used successfully for recovery on tested M8 4G hardware. It is hosted by a separate SourceForge project; verify the package and device compatibility before flashing.

### GOV V14 (partial)

```text
Version:            GOV.V14_20251220
Status:             Partial components only; no standalone ROM
```

GOV V14 boot and AVB components were found in **slot A** of the GOV V15 backup. These components are included in the GOV V15 dump. **Do not treat them as a complete GOV V14 firmware release.**

### GOV V15

```text
Version:            GOV.V15_20260310
Package:            Multilaser_M8_4G_GOV_V15_Recovery_Dump.tar.zst
Status:             Unofficial dump; full restoration untested
```

**Download mirrors**

- [MEGA](https://mega.nz/file/uC4TzDQR#CBrdfWj0EnAgkM_8LvW4uQiMDyh-Jo_DLwpIomNXzIA)
- [Internet Archive](https://archive.org/details/multilaser-m8-4g-gov-v15-20260310)

**Verification**

- [SHA-256 checksum](checksums/Multilaser_M8_4G_GOV_V15_Recovery_Dump.tar.zst.sha256)

The dump contains GOV V14 components in slot A, GOV V15 components in slot B, and a shared `super.bin` with Virtual A/B metadata and COW partitions. A fully bootable restoration from this package has **not** been demonstrated.

## Verifying downloads

Download the matching `.sha256` file from the links above and place it in the same directory as the downloaded archive. On Linux, run:

```sh
sha256sum -c Multilaser_M8_4G_GOV_V3_Public_Recovery_Dump.tar.zst.sha256
```

Or, for GOV V15:

```sh
sha256sum -c Multilaser_M8_4G_GOV_V15_Recovery_Dump.tar.zst.sha256
```

The expected result ends with `OK`. If a checksum fails, **do not flash the file**. Both download mirrors should host byte-for-byte identical copies of each archive so that one checksum applies to both.

A matching checksum confirms that a download matches the published digest; it does not prove the firmware is authentic, safe, compatible, or bootable.

## Recovery precautions

- Confirm the exact tablet model and hardware revision before doing anything.
- Keep a backup of the target device and a known-working recovery path.
- Do not blindly flash the preloader, GPT, or firmware from another tablet variant.
- Never overwrite device-specific identity, calibration, NVRAM, or NVDATA partitions.
- Do not mix slot A and slot B firmware components indiscriminately.
- Do not relock the bootloader with an experimental firmware dump.
- Read the README and flashing guide inside each archive before attempting any recovery.

**GOV V3 and GOV V15 are experimental firmware dumps, not verified installation packages.** Flashing can cause data loss, bootloops, or a device that no longer boots.

## Project status

```text
GOV V3:             MEGA and Internet Archive available
Stock V10:          SourceForge available
GOV V14:            Partial components in GOV V15 dump
GOV V15:            MEGA and Internet Archive available
```

## Contributions

Corrections, verified firmware information, compatibility reports, and documentation improvements are welcome. Do not submit files containing personal data or unique device identifiers.

## Disclaimer

This is an unofficial, independent preservation project and is not affiliated with Multilaser, MediaTek, or Google. Firmware copyrights remain with their respective owners. Hosting or downloading a firmware dump does not itself grant redistribution rights. All recovery operations are at the user's own risk.
