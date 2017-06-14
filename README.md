# razer-blade-stealth-linux
Getting the Razer blade Stealth working with OpenSuse Tumbleweed

The first big issue I had was with a flickering screen.

You can test this fix as follows:
When you boot, press e to edit the boot entry and add i95.enable_psr=0 to the line that begins with "linux". 

If it stops the flickering, you can make it permanent by:

Adding i915.enable_rc6=0 to the below line in /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="resume=/dev/nvme0n1p6 splash=silent quiet showopts i915.enable_rc6=0" 

and then running sudo grub2-mkconfig -o /boot/grub2/grub.cfg

then rebooting and celebrating
