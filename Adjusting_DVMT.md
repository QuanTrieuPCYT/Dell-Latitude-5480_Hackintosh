# Adjusting DVMT
## ⚠ Only appicable for Dell Latitude 5280/5480/5580 and Dell Precision 3520 ⚠
For enabling 4K60p and better graphics performance, you will need to **adjust your DVMT**. **Please note that this guide is only applicable for the Dell Latitude 5280/5480/5580 and the Dell Precision 3520**.

* **Step 1:** Boot up OpenCore and choose `modGRUBShell.efi`.
* **Step 2:** Type `setup_var 0x795 0x2` to set DVMT Pre-allocated to `64M`
* **Step 3:** Type `setup_var 0x796 0x3` to set DVMT Total GFX MEM to `Max`
* **Step 4:** Remove `framebuffer-fbmem` and `framebuffer-stolenmem` if you have in your `config.plist`

**That's all! You have successfully adjusted your DVMT. And please do not reset the BIOS or you will have to do the process again!**
