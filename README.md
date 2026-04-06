# Mi Notebook 14 - macOS Tahoe

> [!IMPORTANT]
> **Platform Info values have been removed** from the config.plist file. **Use GENSMBIOS to generate your own values**. <ins>**Also, check the information below before continuing**<ins>.

For those who can't get macOS Tahoe to work on their **Mi Notebook 14**, here is my EFI folder which works.

## My Laptop Specs:
- **CPU:** Intel Core i5-10210U (Comet Lake Processor)
- **Ram:** 8GB (Soldered)
- **Storage:** 256GB M.2 SATA Samsung SSD
- **Graphics:** Intel Integrated Graphics UHD 620 
- **Audio:** Realtek ALC256


## What works?
Everything you need works. Here is a table of everything that works on macOS Tahoe: 

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
| Speakers & Headphone Jack | ✅ Yes (Using VoodooHDA.kext) |

## Troubleshooting:

### > HELP! I can't connect to the internet during recovery.

**WiFi works using the `itlwm.kext` which requires Heliport to be installed which you don't have inside the recovery**. The hoRNDIS.kext file is included in the EFI Folder. Just **plug in your phone and switch it to `USB Tethering` and then start the installation progress**.

---

### > HELP! I can't connect to the internet inside macOS.

**WiFI works using the `itlwm.kext` which requires Heliport to be installed**. Go to some other device and download the Heliport app from the [GitHub](https://github.com/OpenIntelWireless/heliport). Then, transfer it to your macOS partition, install it, run it and connect to your network.

Voila! You got internet working now. 

> [!TIP]
> Make Heliport to autostart with macOS so you don't have to manually open Heliport to connect to your network everytime you boot into macOS. 

---

### > HELP! I can't listen to any sound in macOS.

**Audio works using VoodooHDA.kext**. In order to get Audio working, go to their [GitHub](https://github.com/CloverHackyColor/VoodooHDA) and download **both** `VoodooHDA.kext.zip` & `VoodooHDA.prefpane.zip`. Unzip both the files. Then, open a terminal wherever both the files are stored and run these commands.

```bash
# Go to the folder containg both the files. Let's take the downloads folder for example:

cd Downloads

# Copy the kext to /Libary/Extensions and fix permissions:
sudo cp -R VoodooHDA.kext /Library/Extensions/
sudo chown -R root:wheel /Library/Extensions/VoodooHDA.kext
sudo chmod -R 755 /Libary/Extensions/VoodooHDA.kext

# Copy the prefpane to /Library/PreferencePanes:
sudo cp -R VoodooHDA.prefpane /Library/PreferencePanes/

```
After executing all those commands, if you see a pop up telling you to allow VoodooHDA.kext, **ALLOW** it. If not, reboot and go into `System Settings > Privacy & Security` and scroll down till you see the option to allow it and then, well, allow it. After allowing the kext, **reboot** again.

Voila! You got audio working now.

---