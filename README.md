# Quick and dirty patch for Mediatek 7922 bluetooth on ~Fedora 36~ Arch Linux

This is a quick and dirty script to enable bluetooth on Mediatek 7922 chips on ~Fedora 36~ Arch Linux (but should work with any distro).

All the bits are already there in order for the chip to work, but for a single entry in a list in btusb.c kernel module that say if you see this id ~13d3:3568~ 0489:e0e2 use Mediatek firmware. Here is the patch to the kernel that fixes the problem: ~https://patchwork.kernel.org/project/linux-mediatek/patch/20220602092822.953521-1-aaron.ma@canonical.com/~ https://lore.kernel.org/all/20220625090358.9373-1-xw897002528@gmail.com/ But until this gets mainlined, every time I update the kernel I have to fix this all over again.

So instead of building a new out of tree module every time I get a kernel update, I just run this script that binary patches the module and removes it's signing keys.
You will need the following packages installed for it to work:
  - ~xz~ zstd
  - binutils

If you prefer to build the module, here is the bug report where I explain how to do it: ~https://bugzilla.redhat.com/show_bug.cgi?id=2091399~
