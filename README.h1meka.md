# h1meka U1tra Kernel for Redmi Note 10 Pro (sweet)

## Status

This is a research and early bring-up project.

- Based on upstream Linux v6.6.
- Not bootable on sweet.
- Not a flashable kernel.
- No release image exists.
- No hardware functionality is claimed.
- Use on a physical device is not currently supported.

## Target

- Xiaomi Redmi Note 10 Pro
- codename `sweet`
- Qualcomm SM7150 / SDMMAGPIE
- arm64

## Current source milestones

Completed public commits:

- minimal SM7150 foundation
- SM7150 CPU topology
- Kryo4xx Gold/Silver CPU compatibles
- SM7150 RPMhCC binding compatible
- SM7150 UFS binding compatible
- 32 kHz sleep-clock provider

## Known blockers

- no board DTS
- RPMh/XO unresolved
- GCC provider blocked
- TLMM tile windows unresolved
- GENI blocked
- UFS host/PHY DTS blocked
- SMMU provider blocked
- PM6150 regulator provider blocked
- no USB, display, modem, audio, Wi-Fi, Bluetooth, charging, camera or Android
  boot support

## Safety

- Do not flash this kernel.
- Do not boot it on a daily-use device.
- No warranty is provided.
- No charging or thermal validation has been performed.
- No KernelSU or SUSFS support is included.
- No overclock support is included.
- No One UI 9 ROM is included.

## Build status

- The upstream arm64 defconfig baseline builds.
- Image, modules and dtbs passed in local compile-only validation.
- The SM7150 DTSI is checked through a temporary wrapper because no board
  target exists.
- Compile success is not hardware validation.

## License

- See `COPYING` and `LICENSES/`.
- The kernel remains under GPL-2.0-only kernel-wide terms, with compatible
  per-file SPDX expressions.
- No conflicting license is added.

## Development branch

Public `main` represents the current reviewed research checkpoint.
See `docs/h1meka-port-status.md` for the port status.
