# Mi Notebook 14 - macOS Tahoe

> [!NOTE]
> Speakers & Headphone Jack currently do **not work**. I have tried everything I could think of to get it to work but unfortunately, I didn't succeed in doing so.

> [!IMPORTANT]
> **Platform Info values have been removed** from the config.plist file. **Use GENSMBIOS to generate your own values**. <ins>**Also, check the information below before continuing**<ins>.

For those who can't get macOS Tahoe to work on their **Mi Notebook 14**, here is my EFI folder which works.

## My Laptop Specs:
- **CPU:** Intel Core i5-10210U (Comet Lake Processor)
- **Ram:** 8GB (Soldered)
- **Storage:** 256GB M.2 SATA Samsung SSD
- **Graphics:** Intel Integrated Graphics UHD 620 


## What works?
**Almost** everything you need works. Here is a table of everything that works on macOS Tahoe: 

| Component | Works?
| --------| --------|
| Inbuilt Display | ✅ Yes|
| WiFi |✅ Yes (Using itlwm.kext. **Therefore, some features of macOS may not work.** )|
| BlueTooth | ✅ Yes |
| Keyboard | ✅ Yes |
| Trackpad | ✅ Yes |
| USB | ✅ Yes |
| Brightness & Volume Keys| ✅ Yes |
| Sleep | ✅ Yes |
| Speakers & Headphone Jack | ❌ **No** (If you have the fix, please create a pull request and i'll look into it) |

## Troubleshooting:

### > HELP! I can't connect to the internet during recovery.

**WiFi works using the `itlwm.kext` which requires Heliport to be installed which you don't have inside the recovery**. The hoRNDIS.kext file is included in the EFI Folder. Just **plug in your phone and switch it to `USB Tethering` and then start the installation progress**.

### > HELP! I can't connect to the internet inside macOS.

**WiFI works using the `itlwm.kext` which requires Heliport to be installed**. Go to some other device and download the Heliport app from the [GitHub](https://github.com/OpenIntelWireless/heliport). Then, transfer it to your macOS partition, install it, run it and connect to your network.

Voila! You got internet working now. 

> [!TIP]
> Make Heliport to autostart with macOS so you don't have to manually open Heliport to connect to your network everytime you boot into macOS. 

---
