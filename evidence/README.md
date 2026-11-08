# Evidence

Real, unedited screenshots. Items with a **_MARKED** copy also include the clean
original, so the yellow highlights can be checked against the unaltered source.

## 1. Device runs kernel 5.15.194 (real phone)

Settings → About phone. Kernel version:
`5.15.194-android13-8-00019-gf4321180a397-ab15212794`.

![Device About phone — kernel 5.15.194](1_device_kernel_5.15.194_MARKED.png)

Clean original: [`1_device_kernel_5.15.194.png`](1_device_kernel_5.15.194.png)

## 2. The GKI core commit is a public Google AOSP tag

`android.googlesource.com/kernel/common`, tag `android13-5.15-2025-12_r9` →
`object f4321180a3973d19…` — the exact commit named in the device string
(`gf4321180a397`). The build artifact `15212794` also matches the device's
`ab15212794`.

![Google AOSP tag android13-5.15-2025-12_r9 — commit f4321180a397](4_aosp_tag_commit_f4321180a397.png)

## 3. That tag's Makefile is Linux 5.15.194

Same Google tree, the `Makefile` at that tag: `VERSION = 5`, `PATCHLEVEL = 15`,
`SUBLEVEL = 194`.

![Google AOSP Makefile at the tag — SUBLEVEL = 194](5_aosp_makefile_sublevel194.png)

## 4. Xiaomi's published vendor tree is kernel 5.15.94

`github.com/MiCode/Xiaomi_Kernel_OpenSource`, branch `air-t-oss`, `Makefile`
(`VERSION = 5`, `PATCHLEVEL = 15`, `SUBLEVEL = 94`). This is the **vendor tree**
(modules, defconfig, device trees) — a different component from the GKI core,
and it need not share the core's sublevel.

![MiCode air-t-oss Makefile — kernel 5.15.94](2_micode_published_source_5.15.94_MARKED.png)

Clean original: [`2_micode_published_source_5.15.94.png`](2_micode_published_source_5.15.94.png)

## 5. Device open-source page offers license texts only

Settings → Open source licenses, on the device — license texts (by content
hash), no kernel-source download. (Source is obtained from the public repos
above, not from this page.)

![Device Open source licenses page](3_device_opensource_page_MARKED.png)

Clean original: [`3_device_opensource_page.png`](3_device_opensource_page.png)

---

**Summary:** the device ships GKI kernel **5.15.194** (its source is Google's
public ACK tag `android13-5.15-2025-12_r9`, commit `f4321180a397`), and Xiaomi
publishes the matching **vendor tree** (5.15.94) on MiCode. Both halves of the
corresponding source are public and shown above in real screenshots.
