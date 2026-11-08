# Device identification

Raw values read from the device (via `adb getprop` / `uname -r`).

```
ro.product.model             = 23124RN87I
ro.product.device            = air
ro.build.fingerprint         = Redmi/air_in/air:15/AP3A.240905.015.A2/OS2.0.208.0.VGQINXM:user/release-keys
ro.build.version.incremental = OS2.0.208.0.VGQINXM
ro.build.version.release     = 15            (Android 15)
ro.build.id                  = AP3A.240905.015.A2
ro.build.version.security_patch = 2026-08-01
ro.mi.os.version.name        = OS2.0         (HyperOS 2.0)
kernel (uname -r)            = 5.15.194-android13-8-00019-gf4321180a397-ab15212794
```

## Where this kernel's source lives (GKI device)

**GKI core** — the `Image`, from Google's Android Common Kernel:

```
Repo    : android.googlesource.com/kernel/common
Branch  : android13-5.15
Tag     : android13-5.15-2025-12_r9   (commit f4321180a397 - matches the g<hash> in uname)
Makefile: VERSION = 5 / PATCHLEVEL = 15 / SUBLEVEL = 194   ->   Linux 5.15.194
```

**Vendor tree** — modules, defconfig, device trees, from Xiaomi MiCode:

```
Repo    : github.com/MiCode/Xiaomi_Kernel_OpenSource
Branch  : air-t-oss   (commit 13290e766)
Makefile: VERSION = 5 / PATCHLEVEL = 15 / SUBLEVEL = 94    ->   kernel 5.15.94
MTK GPL modules: github.com/MiCode/MTK_kernel_modules  (branch air-t-oss)
```

The `g<hash>` field (`gf4321180a397`) in the kernel string is the exact Google
ACK commit the GKI core was built from, so the core source is public and
precisely identified. The GKI core (5.15.194, Google) and the vendor tree
(5.15.94, MiCode) are different components with independent version numbers —
both published. Complete corresponding source = GKI core + vendor tree.
