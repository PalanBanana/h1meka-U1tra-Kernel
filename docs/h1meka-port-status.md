# h1meka U1tra Kernel Port Status

## Public checkpoint

- Upstream base: Linux v6.6.
- Public `main` is the reviewed research checkpoint: six SM7150 source commits
  on top of the upstream base, followed by this documentation commit.
- The checkpoint is not bootable on sweet and is not a flashable kernel.

## Completed source work

- arm64 DTS: minimal SM7150 foundation (root node, zero-size memory
  placeholder, PSCI, architectural timer, simple-bus SoC node, GICv3).
- arm64 DTS: SM7150 CPU topology (eight CPU nodes, 6+2 cpu-map). This is a
  declaration only; no board DTS consumes it.
- dt-bindings: Qualcomm Kryo4xx Gold and Silver CPU compatibles.
- dt-bindings: SM7150 RPMhCC compatible.
- dt-bindings: SM7150 UFS compatible.
- arm64 DTS: SM7150 32 kHz sleep-clock provider.

## Compile-only validation

- The upstream arm64 defconfig baseline builds.
- Image, modules and dtbs passed in local compile-only validation.
- The SM7150 DTSI is checked through a temporary wrapper because no board
  target exists.
- No runtime validation has been performed. No device has booted this kernel.

## Frozen subsystems

These remain frozen until their dependencies are resolved:

- RPMh/XO: unresolved.
- GCC provider: blocked.
- TLMM tile windows: unresolved.
- GENI: blocked.
- UFS host and PHY DTS: blocked.
- SMMU provider: blocked.
- PM6150 regulator provider: blocked.

No USB, display, modem, audio, Wi-Fi, Bluetooth, charging, camera or Android
boot support exists.

## Device-test boundary

- Device testing is outside the scope of the public checkpoint.
- No flashing, booting or hardware validation is claimed or supported.
- Compile success is not hardware validation.

## Planned order

1. foundational providers
2. board DTS
3. early serial and memory
4. UFS
5. QUSB2 high-speed device path
6. DPU/DSI/K6 panel
7. modem/IPA
8. audio
9. Wi-Fi/Bluetooth
10. charger/fuel-gauge/thermal
11. camera/sensors
12. Android 17 requirements
13. KernelSU/SUSFS only after vanilla boot
14. performance only after stability
15. overclock only after validated thermal protection

## Contributions

Contributions must follow these rules:

- Changes must be evidence-backed.
- Each patch must cover one logical subsystem.
- No proprietary blobs may be included.
- No donor-device DTS values may be copied.
- No success claim may be made without build or runtime evidence.

## License and provenance

- The kernel remains under the upstream licensing structure: `COPYING`,
  `LICENSES/`, and GPL-2.0-only kernel-wide terms.
- Existing SPDX identifiers and upstream notices are preserved.
- Original upstream authorship and commit metadata are preserved.
- No new top-level license conflicts with the Linux licensing structure.
- No Signed-off-by lines were added retroactively.
