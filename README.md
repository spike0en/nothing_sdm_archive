# Nothing Phone (2) Archive

* A comprehensive collection of unmodified Stock OTA images for Nothing Phone (2).

## Downloads

- Downloads are tagged with `POST_OTA_VERSION` & `NothingOS version` [here](https://github.com/spike0en/Nothing_SDM_Archive/releases?q=pong&expanded=true).

- Official Full OTA Update Package is marked `-FullOTA`. Extract the splitted 7z parts to get the `<name>-FullOTA.zip`.

## Categories

- The Stock OTA image files are categorized and archived in .7z format based on `boot`, `logical`, and `firmware` categories.

### Boot (marked `-image-boot.7z`)

Includes 7 images:
```bash
boot, dtbo, vendor_boot, recovery, vbmeta, vbmeta_system & vbmeta_vendor
```
### Logical (marked `-image-logical.7z.001-003`)

Includes 6 images:
```bash
system, system_ext, product, vendor, vendor_dlkm & odm
```
### Firmware (marked `-image-firmware.7z`)

Includes 23 images:
```bash
abl, aop, aop_config, bluetooth, cpucp, devcfg, dsp, featenabler, hyp, imagefv, keymaster, modem, multiimgoem, multiimgqti, qupfw, qweslicstore, shrm, tz, uefi, uefisecapp, xbl, xbl_config & xbl_ramdump
```

## Disclaimer

- While this is a collection of unmodified images, you still need to have the bootloader unlocked.

- You can re-lock the bootloader after flashing images.

- SHA-1 hash of `<name>-FullOTA.zip` file has been provided. It is to be noted that the built-in NothingOS Offline Updater Tool autonomously verifies file integrity. It initiates the update process only if the file aligns with the hash values specified in `payload-properties.txt`, which is obtained during the creation of the update package.

- It's important to note that full OTA packages may not be consistently available with every release. 

- For further inquiries, discussions, and engaging content, users are encouraged to explore the [Nothing Phone (2) Telegram Community](https://t.me/NothingPhone2)

## Fastboot Flashing

- To flash the stock, unmodified images with fastboot, extract the files using 7z and use [Pong_fastboot_flasher](https://github.com/HELLBOY017/Pong_fastboot_flasher).

- Please download and use the latest fastboot [directly from Google](https://developer.android.com/tools/releases/platform-tools). Compatible USB drivers can be obtained from [here](https://developer.android.com/studio/run/win-usb).

- If you optionally want to have dm-verity disabled, perform:

```bash
  fastboot update --disable-verity --disable-verification vbmeta.img
```
- Alternatively users can follow this [detailed guide](https://telegra.ph/Guide-for-flashing-Stock-ROM-on-Nothing-Phone-2-04-22).

## Manual Sideloading of Full OTA Packages

### A. Via Stock Nothing Offline OTA Updater Tool (Locked BL): 

1. To flash stock, unmodified official Full OTA packages, extract the files using 7z to obtain the <name>-FullOTA.zip file.
2. Using your preferred file manager, create a folder named 'ota' at the root of your storage.
3. Copy the <name>-FullOTA.zip into the newly created 'ota' folder.
4. Open your dial pad and type `*#*#682#*#*`.
5. The manual update utility will launch, scanning and locating your previously downloaded update file.
6. Tap to begin the update. The process will take about 10-15 minutes (duration may vary).
7. Enjoy your updated device after reboot!

### B. Via Custom Recovery (Unlocked BL):

- Alternatively, users can directly flash these full OTA packages using available custom recoveries for Nothing Phone (2), such as [TWRP](https://xdaforums.com/t/recovery-12-unofficial-teamwin-recovery-project.4623971) or [OrangeFox](https://xdaforums.com/t/recovery-12-1-official-orangefox-recovery-project-ofrp.4631141).


## NothingMuchROM

- You can use this repository to flash non-super partitions to the latest stock to be used with [NothingMuchROM by arter97](https://xdaforums.com/t/nothingmuchrom-for-nothing-phone-2.4623411).

- Skip downloading `-logical` files, and follow the above steps but answer "N" to Flash logical partition images? during [Pong_fastboot_flasher](https://github.com/HELLBOY017/Pong_fastboot_flasher)'s installation.


## Integrity Check

- You can check the downloaded file's integrity with one of the following commands :

``` bash
  md5sum -c *-hash.md5
  sha1sum -c *-hash.sha1
  sha256sum -c *-hash.sha256
  xxh128sum -c *-hash.xxh128
```

- xxh128 is usually the fastest.


### Thanks to
- [luk1337](https://github.com/luk1337/oplus_archive) & [arter97](https://github.com/arter97/nothing_archive) for their great work!
- [Hellboy017](https://github.com/HELLBOY017) for his assistance to make the [Pong Fastboot Flasher](https://github.com/HELLBOY017/Pong_fastboot_flasher).
