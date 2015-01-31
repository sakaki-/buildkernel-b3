# buildkernel-b3
Script to build a bootable Linux kernel for the Excito B3.

## Description

<img src="https://raw.githubusercontent.com/sakaki-/resources/master/excito/b3/Excito_b3.jpg" alt="Excito B3" width="250px" align="right"/>
**buildkernel-b3** is a script that builds a Gentoo Linux kernel image suitable for booting either from the B3's internal disk (default), or from a USB key (when the **--usb** option is specified).

It automatically prepends the necessary code to temporarily switch off the L2 cache during early boot (per [this note](https://lists.debian.org/debian-boot/2012/08/msg00804.html)) and appends the kirkwood-b3 device tree blob.

**buildkernel-b3** should be run as root, in the top level kernel source directory. You will need an appropriate `.config` file in place when building the kernel.

You can run **buildkernel-b3** either on the B3 directly, or on a Gentoo PC (with an appropriately configured `crossdev` setup).

If running on a PC, a directory `deploy_root` will be created as a result of running the script, with the necessary files for you to copy across to your B3.

If running on the B3 natively, the files (kernel, modules, config and System.map) will be moved to the correct positions for you (and prior copies of all but the modules backed up).

Please see the included manpage for further details.

## Installation

**buildkernel-b3** is best installed (on Gentoo) via its ebuild, available as part of the [**gentoo-b3** overlay](https://github.com/sakaki-/gentoo-b3-overlay).
