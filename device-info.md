# Device identification

Raw values read from the device (via `adb getprop` / `uname -r`). These identify
the exact build the Corresponding Source must match.

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

## Published source for this device

```
Repo    : github.com/MiCode/Xiaomi_Kernel_OpenSource
Branch  : air-t-oss   (the only branch for codename `air`)
Commit  : 13290e766   "Kernel: Xiaomi kernel changes for Redmi 13R 5G/Redmi 13C 5G Android T"
Makefile: VERSION = 5 / PATCHLEVEL = 15 / SUBLEVEL = 94   ->   kernel 5.15.94
MTK GPL modules: github.com/MiCode/MTK_kernel_modules  (branch air-t-oss)
```

**Shipped kernel 5.15.194  vs  published source 5.15.94  →  does not correspond.**
