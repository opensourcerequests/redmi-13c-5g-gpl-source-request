# Redmi 13C 5G (air) — GPL Corresponding Source Request & Compliance Check

A good-faith open-source compliance check on a **Xiaomi Redmi 13C 5G**, and a
**GPLv2 Section 3(b)** request for the Corresponding Source that matches the
kernel actually shipped on the device.

## Device

| Field | Value |
|---|---|
| Model | 23124RN87I (Redmi 13C 5G) |
| Codename | `air` (MediaTek Dimensity 6100+) |
| OS build | OS2.0.208.0.VGQINXM (Android 15 / HyperOS 2.0) |
| **Kernel (shipped)** | **5.15.194** |
| Security patch | 2026-08-01 |

## The finding — Corresponding-Source currency gap

- The device ships kernel **5.15.194**.
- The only kernel source Xiaomi publishes for this device is branch
  **`air-t-oss`** on `github.com/MiCode/Xiaomi_Kernel_OpenSource`, which is
  kernel **5.15.94** (verified: it is the *only* `air` branch, and its
  `Makefile` shows `VERSION = 5`, `PATCHLEVEL = 15`, `SUBLEVEL = 94`).
- Therefore the **published source does not correspond to the shipped binary.**
  GPLv2 §3 requires the *corresponding* source — same version and modifications
  as the conveyed executable.

## What was verified

- **Source availability** — kernel source is posted on MiCode (`air-t-oss`) with
  the matching MediaTek GPL modules, and the device carries a GPLv2 §3(b) written
  offer (`oss-request@xiaomi.com`, valid 3 years, to any third party).
- **Buildability** — the published `air-t-oss` source **compiles into a bootable
  ARM64 kernel image**. It was built with LTO and BTF disabled and the generic
  `gki_defconfig` to fit the build host, so it is **not byte-identical** to the
  shipped kernel (that needs Google's pinned clang + ThinLTO + the device vendor
  config). But the published source is genuine, complete, and builds.
- **Build scripts (§3)** — present (`build.config.mtk.aarch64`, Kbuild/Kconfig,
  defconfigs).
- **Copyright preservation in source (§1)** — the kernel source retains upstream
  copyright headers (e.g. `kernel/sched/core.c` → Linus Torvalds) + SPDX tags.
- **On-device open-source page** — surfaces license *texts* only; it offers no
  kernel-source download.
- **Full license / obligation audit** — see [`audit/`](audit/): 63 copyleft
  components mapped; the AGPL and `lzma` classifier flags resolved as false
  positives; attribution notes included.

## The request

A GPLv2 §3(b) request was sent to **`oss-request@xiaomi.com`** asking for the
complete Corresponding Source matching the shipped **5.15.194** build — kernel +
build/install scripts + the device vendor config fragments + the MTK GPL kernel
modules. Full text: [`source-request-email.md`](source-request-email.md).

## Evidence

See [`evidence/`](evidence/) — screenshots in clean and yellow-marked pairs:

1. Device **About phone** → kernel **5.15.194**
2. MiCode `air-t-oss` **Makefile** → kernel **5.15.94**
3. Device **Open source licenses** page → license texts only

## Status

- Request sent: _2026-11_ (awaiting response).
- Follow-up plan: nudge at ~3 weeks, again at ~5 weeks; escalate to the
  [Software Freedom Conservancy](https://sfconservancy.org/copyleft-compliance/)
  (`compliance@sfconservancy.org`) only if unanswered after ~6–8 weeks.

## Note

This is a good-faith compliance exercise, **not legal advice**. Under the GPL,
the duty to provide Corresponding Source runs from the distributor (Xiaomi) to
recipients of the binary.
