# GPLv2 Section 3(b) source request — email sent to Xiaomi

**To:** oss-request@xiaomi.com
**Subject:** Thank you + GPLv2 Section 3(b) source request — Redmi 13C 5G (air), build OS2.0.208.0.VGQINXM

---

Dear Xiaomi Open Source Team,

First, thank you for the care Xiaomi puts into its open-source program. I was
able to take the published kernel source for my device (the `air-t-oss` branch on
`github.com/MiCode/Xiaomi_Kernel_OpenSource`), together with the build
configuration you provide, and compile it cleanly into a working kernel. A
published source tree that actually builds is genuinely appreciated — it is not
something every vendor gets right — and the on-device source notices and contact
address made everything easy to find. Thank you for maintaining this so well.

I am writing with one small follow-up. The branch I built from is kernel
5.15.94, while my device ships kernel 5.15.194:

- Model: 23124RN87I (Redmi 13C 5G)
- Codename / platform: air (MediaTek)
- Build fingerprint: Redmi/air_in/air:15/AP3A.240905.015.A2/OS2.0.208.0.VGQINXM:user/release-keys
- HyperOS build: OS2.0.208.0.VGQINXM (Android 15)
- Kernel version: 5.15.194
- Security patch level: 2026-08-01

I note that the only published branch for this device (`air-t-oss` on
`github.com/MiCode/Xiaomi_Kernel_OpenSource`) is kernel 5.15.94, which predates
the 5.15.194 kernel actually shipped on this build; I was not able to find any
published branch corresponding to this build. I am therefore requesting the
source that corresponds to the binary I received.

Under the written offer in the device's open-source notices (and GNU GPL v2
Section 3(b)), I would be grateful if you could provide the complete
Corresponding Source that matches this exact build, including:

1. The kernel source for 5.15.194 as shipped, with the scripts used to control
   compilation and installation (Kbuild/Kconfig, the build.config files, and the
   defconfig and vendor configuration fragments needed to reproduce it);
2. The corresponding MediaTek GPL kernel modules for this build; and
3. Source for any other GPL/LGPL userspace components in this build that are not
   already published.

A download link — or a MiCode branch corresponding to this build — would be
perfect; there is no need to ship physical media.

Thank you again for your work on this, and for supporting the open-source
community.

Best regards,
Open Source
