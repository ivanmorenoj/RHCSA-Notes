#  Interrupt the Boot Process to Gain Access to a System

## rescue root passwd

1. reboot machine
2. interrupt grub process typing any key
3. press 'e' to edit the kernel that you wanto to init
4. locate 'linux16' line and add at the end of the line 'rd.break' anpress Ctrl-x
5. the sysroot is mounted as only read filesystem, remount with rw filesystem
6. mount -o remount,rw /sysroot
7. chroot /sysroot
8. type passwd command and change password
9. touch /.autorelabel
10. exit 





