# Nothing Phone (3a) Pro (`nothing-asteroids`)

This is the device-specific **contribution workspace**, not a firmware download.
[The canonical device record](https://github.com/omnipha/ports/blob/main/devices/nothing-asteroids/device.yaml) owns every Omnipha support and release claim; this README is a snapshot from provisioning and may become stale. Check the record before reporting status.

| Fact | Value at repository creation |
| --- | --- |
| Vendor / SoC | Nothing / `sm7635` |
| Reported components | boot=untested, ssh=untested, wifi=untested |
| Release | unreleased (check the canonical record for changes) |
| Kernel policy | [omnipha/linux-sm7635](https://github.com/omnipha/linux-sm7635) (`AGENTS.md`) |
| Packages | [ports/devices/nothing-asteroids](https://github.com/omnipha/ports/tree/main/devices/nothing-asteroids) |
| Image definition | [omnipha/images](https://github.com/omnipha/images/tree/main/devices/nothing-asteroids) (may not exist yet) |
| All phones | [ports/DEVICES.md](https://github.com/omnipha/ports/blob/main/DEVICES.md) |

## Where to help on this phone

[The full-port mission](https://github.com/omnipha/ports/issues/3) tracks
Nothing Phone (3a) Pro and its physical acceptance gates. The public hardware
matrix already has component-specific issues in `ports`; those issues remain
the original source of test procedure and dependency status. **Do not duplicate
them here.** Contribute logs or propose a test by commenting on the linked
issue or by opening a new device-specific report here with a reverse link:

- [First Omnipha boot and USB SSH](https://github.com/omnipha/ports/issues/6):
  untested, blocked on an actual image and a separately approved physical test.
- [WiFi and Bluetooth radio](https://github.com/omnipha/ports/issues/7),
  [display/touch/GPU](https://github.com/omnipha/ports/issues/8),
  [audio](https://github.com/omnipha/ports/issues/9),
  [modem/SIM](https://github.com/omnipha/ports/issues/10),
  [sensors/GPS/NFC](https://github.com/omnipha/ports/issues/11),
  [haptics/LEDs](https://github.com/omnipha/ports/issues/12),
  [battery/thermal/suspend](https://github.com/omnipha/ports/issues/13), and
  [cameras](https://github.com/omnipha/ports/issues/14): all untested on an
  Omnipha boot, not evidence of functioning drivers.
- [Server-image build](https://github.com/omnipha/images/issues/1) depends on
  [headless builder support](https://github.com/omnipha/builder/issues/1).
  Current `image.yaml` is only validated, not built or released.

The repo name is device-specific, but kernel work for SM7635 is shared; read
[linux-sm7635/AGENTS.md](https://github.com/omnipha/linux-sm7635/blob/main/AGENTS.md)
before opening a patch. A contributor cannot infer device support from a
compiler success or a temporary debug boot. Never upload raw stock dumps,
identifying logs or private keys.

## Can I install Omnipha?

`status.boot: works`, a kernel build, an APKBUILD or an `image.yaml` does **not** mean an Omnipha image exists. Only `release.status: testing` or `official` in the canonical device record indicates a public image with SHA-256, build manifest, verified physical boot and a reviewed device-specific flashing **and rollback** guide. If it says `unreleased` or no release record exists, there is no Omnipha download or safe public flash procedure for this phone. `flash: fastboot` is metadata, not instructions. Do not flash from this README or an issue.

## Reproduce a result or contribute

1. Find an existing issue here (if this repo is new, see linked bring-up work in `ports`) before filing another. Check the device variant and the canonical component status; `untested` is not `broken`.
2. On hardware already running a known test setup, report the exact image/kernel identity, variant, date, redacted logs, expected versus observed outcome, and a safe way to reproduce it. Do not distribute stock dumps, proprietary firmware, keys, or device identifiers. Physical writes require the operator's explicit authorization and verified rollback.
3. Link your issue or PR to the implementation repo: shared kernel work follows [omnipha/linux-sm7635](https://github.com/omnipha/linux-sm7635)'s source policy; device packages go to [ports](https://github.com/omnipha/ports); image build work goes to [images](https://github.com/omnipha/images). Leave a reverse link here.
4. After the implementation and public hardware evidence land, open a **separate linked ports PR** updating `devices/nothing-asteroids/device.yaml` and `status_evidence`. A PR cannot span repositories. Run the ports index and tests; do not claim a measured boot from CI alone. The release owner and tester review the published artifact and rollback before a status becomes `testing` or `official`.

## Ownership and retirement

This repo owns only device-specific issues, logs with sensitive data removed, and safe test plans. The ports device record owns facts. Creating a device repo neither enrolls it in the org-wide agent queue nor assigns a supervisor or release owner. Retire by archiving the repo after linking the history from ports; do not delete history or a shared SoC kernel repo.
