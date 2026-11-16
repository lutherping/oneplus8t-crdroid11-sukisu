# OnePlus 8T (`kebab`) crDroid 11 SukiSU-Ultra + SuSFS Kernel Builder

Automated GitHub Actions kernel builder matching **crDroid 11.13 (Android 15, `15.0`)** for **OnePlus 8T (`kebab`)**:

- **Kernel Source**: [`crdroidandroid/android_kernel_oneplus_sm8250`](https://github.com/crdroidandroid/android_kernel_oneplus_sm8250) (branch `15.0`, `4.19.325-Sirius+`)
- **Root / KPM**: [`SukiSU-Nova/SukiSU-Nova`](https://github.com/SukiSU-Nova/SukiSU-Nova) (branch `builtin`, with `CONFIG_KPM=y` + `patch_linux`)
- **Root Hiding**: SuSFS v2.4.0 (`susfs_patch_to_4.19.patch` from [`NonGKI_Kernel_Build_2nd`](https://github.com/JackA1ltman/NonGKI_Kernel_Build_2nd)) + tailored `scripts/apply_sukisu_susfs_hooks.py`
- **Packaging**: [`osm0sis/AnyKernel3`](https://github.com/osm0sis/AnyKernel3) (`split_boot` / `flash_boot` preserving stock crDroid ramdisk and DTB)

## Usage

1. Run **Actions → Build OnePlus 8T (kebab) crDroid 11 SukiSU Kernel → Run workflow**.
2. Download the `OnePlus8T-crDroid11-SukiSU-Kernel` artifact containing `AnyKernel3-*.zip` and raw `Image`.
3. Ensure Magisk is uninstalled / stock `boot.img` is restored, then flash `AnyKernel3-*.zip` via crDroid Recovery `adb sideload` (or repack `Image` into stock `boot.img` and `fastboot flash boot`).
4. Install the SukiSU-Ultra Manager APK (`com.sukisu.nova`).

## Credits & License

- `crdroidandroid`, `SukiSU-Ultra / SukiSU-Nova`, `simonpunk (susfs4ksu)`, `JackA1ltman (NonGKI_Kernel_Build_2nd)`, `osm0sis (AnyKernel3)`.
- Licensed under **GPL-2.0 / GPL-3.0** compatible terms matching the upstream Linux kernel and build scripts.
