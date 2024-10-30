## Background

Ubuntu 22.04 is using wayland display server. Apps either use wayland natively , or via an X / xorg compatibility layer. (Xwayland). See also How can I tell if an application is using XWayland

On my box, most apps are native wayland, but firefox by default is using Xwayland.

## Improve scroll speed for firefox

You can make firefox to use native wayland instead of Xwayland and for me it is improving the scroll speed ( slowing it down ). How to do it:

    Enter sudo gedit /etc/environment
    Add one line at the end of the file, containing this string: MOZ_ENABLE_WAYLAND=1
    Reboot system


[Source](https://ubuntuhandbook.org/index.php/2022/09/enable-wayland-firefox-chrome/)
[Source 2](https://askubuntu.com/questions/1413750/how-to-change-2-finger-touchpad-scroll-speed-on-ubuntu-22-04)



## Stop kinetic scrolling:
Go to about:config and set "apz.gtk.kinetic_scroll.enabled" to false.
