# Linux Xertz Kernel

This is my custom kernel for Linux Xertz.

Installation

first type
```
make
```
to prepare the kernel.
Then grab a cup of coffee and a blanket and type
```
make modules_install
```
to compile the modules.
Next copy the kernel to the /boot firectory
```
cp -v arch/x86/boot/bzImage /boot/vmLinuz-5.15.11-linux-xertz
```
Next makethe initial ram disk
```
mkinitcpio -k 5.15.11 -c /etc/mkinitcpio.conf -g /boot/initramfs-5.15.11-linux-xertz.img
```
Then, copy System.map
```
cp System.map /boot/System.map-5.15.11-linux-xertz
```
Finally, update grub.
```
grub-mkconfig -o /boot/grub/grub.cfg
```
And there you go! now you have my super cool kernel installed on your computer.


Linux kernel
============

There are several guides for kernel developers and users. These guides can
be rendered in a number of formats, like HTML and PDF. Please read
Documentation/admin-guide/README.rst first.

In order to build the documentation, use ``make htmldocs`` or
``make pdfdocs``.  The formatted documentation can also be read online at:

    https://www.kernel.org/doc/html/latest/

There are various text files in the Documentation/ subdirectory,
several of them using the Restructured Text markup notation.

Please read the Documentation/process/changes.rst file, as it contains the
requirements for building and running the kernel, and information about
the problems which may result by upgrading your kernel.
