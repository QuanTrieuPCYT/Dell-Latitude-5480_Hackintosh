# Disable CFG Lock (my 1 hour of researching)
## ⚠ Only appicable for Dell Latitude 5280/5480/5580 and Dell Precision 3520 ⚠

So you're here because you just want to unlock the CFG Lock of your bad boi right?
You will need the followings:
* `ControlMsr32.efi` (or `VerifyMsr32.efi`) - bundled with [**OpenCorePkg**](https://github.com/acidanthera/OpenCorePkg) in your `/EFI/OC/Tools`
* `modGRUBShell.efi` - download [**here**](https://github.com/datasone/grub-mod-setup_var)

## Check if you have CFG Lock enabled or not
Boot up OpenCore and choose `ControlMsr32.efi`. It should show you one of the followings:

![image1](https://user-images.githubusercontent.com/73286927/134888903-edbfc222-0fcf-4aab-98bc-b1b4d3d58725.jpg)

`This firmware has UNLOCKED MSR 0xE2 register!` - means CFG Lock is disabled

![image2](https://user-images.githubusercontent.com/73286927/134888940-9dbc0031-0e49-4b0f-a93b-3e31a558e455.jpg)

`This firmware has LOCKED MSR 0xE2 register!` - means CFG Lock is enabled

For the former, go into your `config.plist` of OpenCore and set both `AppleCpuPmCfgLock` and `AppleXcpmCfgLock` to `FALSE` then you can close this page. **Don't reset your BIOS or the CFG Lock will be enabled again**.

For the latter, please continue.

## Disabling your CFG Lock
Boot up OpenCore and choose `modGRUBShell.efi`. You should be greeted with a friendly GRUB shell.

Next, type `setup_var 0x4ED 0x00`.

![image0](https://user-images.githubusercontent.com/73286927/134889253-9cf3f931-7c3a-4353-bf26-84c0cacb0bb7.jpg)

After doing the commands, if it shows no error (like the image above), **please shutdown your PC and turn it on again**. After that, boot OpenCore and select `ControlMsr32.efi` to see if your CFG Lock is disabled or not.

If it shows `This firmware has UNLOCKED MSR 0xE2 register!` then you successfully unlocked your CFG Lock! **Also please don't reset your BIOS, or your CFG Lock will be enabled again after doing so**.

Finally, go into your `config.plist` of OpenCore and set both `AppleCpuPmCfgLock` and `AppleXcpmCfgLock` to `TRUE`, then boot macOS as normal. After all of the above steps, you should have better CPU Power Management.
