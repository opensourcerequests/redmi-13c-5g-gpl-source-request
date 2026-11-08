# Evidence

Each item has a **clean** original and a **_MARKED** version (yellow highlights).
Both are included so the highlights can be checked against the unaltered source.

## 1. Device runs kernel 5.15.194

Settings → About phone, on the device.

![Device About phone — kernel 5.15.194](1_device_kernel_5.15.194_MARKED.png)

Clean original: [`1_device_kernel_5.15.194.png`](1_device_kernel_5.15.194.png)

## 2. Published MiCode source is kernel 5.15.94

`github.com/MiCode/Xiaomi_Kernel_OpenSource`, branch `air-t-oss`, `Makefile`
(`VERSION = 5`, `PATCHLEVEL = 15`, `SUBLEVEL = 94`).

![MiCode air-t-oss Makefile — kernel 5.15.94](2_micode_published_source_5.15.94_MARKED.png)

Clean original: [`2_micode_published_source_5.15.94.png`](2_micode_published_source_5.15.94.png)

## 3. Device open-source page offers license texts only

Settings → Open source licenses, on the device — license texts (by content hash),
no kernel-source download.

![Device Open source licenses page](3_device_opensource_page_MARKED.png)

Clean original: [`3_device_opensource_page.png`](3_device_opensource_page.png)

---

**Summary:** device ships **5.15.194**, the only published Corresponding Source is
**5.15.94**, and the on-device page provides no source for it.
