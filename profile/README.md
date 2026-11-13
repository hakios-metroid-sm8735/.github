# HakiOS on the Nothing Phone (3)

The reference for booting [HakiOS](https://github.com/oosexgang/hakios-xnu-kernel), Apple's open-source Darwin
kernel (XNU) for Android phones, on the **Nothing Phone (3)** (`metroid`, Qualcomm SM8735 "Tuna").

**Start here:** [hakios-device-metroid/docs/booting.md](https://github.com/hakios-metroid-sm8735/hakios-device-metroid/blob/main/docs/booting.md)

## Where it stands

| Part | Status |
|---|---|
| Boot from RAM through HakiOS U-Boot (`fastboot boot`, nothing flashed) | works |
| XNU kernel, first user-space program (`hello`) | works, on one core |
| Display (ABL's framebuffer, 1260x2800) | partial: no GPU |
| USB for `xl` (logs, runs, reboot) | partial: as ABL leaves it |
| Darwin user space (lock screen, home screen) | next |
| Touch, buttons, all cores, storage, GPU, audio, Wi-Fi, modem | not yet |

The full record is [`device.conf`](https://github.com/hakios-metroid-sm8735/hakios-device-metroid/blob/main/device.conf).

## Repositories

| Repository | Contents |
|---|---|
| [hakios-device-metroid](https://github.com/hakios-metroid-sm8735/hakios-device-metroid) | the device: configuration, SM8735 SoC layer, U-Boot files, tools, the booting guide |
| [hakios-xnu-kernel](https://github.com/hakios-metroid-sm8735/hakios-xnu-kernel/tree/metroid) (branch `metroid`) | HakiOS's common repository with the loader's `metroid` platform; `tools/hakios-device.py sync` fetches the device repository |

## What is never here

No vendor firmware, no Apple software, no phone serial numbers. The Darwin user space comes from an Apple
restore image you get yourself. Apple's services do not work.

This is an independent research project. It is not affiliated with Apple, Nothing, Qualcomm, or the HakiOS
team.
