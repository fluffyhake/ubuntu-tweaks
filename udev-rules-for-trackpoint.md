## The trackpoint very fast in Ubuntu 24.04

To fix this you can tweak the udev by adding the following to a file in /etc/udev/rules.d/10-trackpoint.rules:


```
ACTION=="add", SUBSYSTEM=="input",
ATTR{name}=="TPPS/2 IBM TrackPoint",
ATTR{device/sensitivity}="90"
ATTR{device/speed}="80",
ATTR{device/inertia}="6",
ATTR{device/press_to_select}="0"
```

This works, which is quite weird. The device is called something else when running "sudo libinput list-devices"

```
Device:           TPPS/2 Elan TrackPoint
Kernel:           /dev/input/event6
Group:            8
Seat:             seat0, default
Capabilities:     pointer 
Tap-to-click:     n/a
Tap-and-drag:     n/a
Tap drag lock:    n/a
Left-handed:      disabled
Nat.scrolling:    disabled
Middle emulation: disabled
Calibration:      n/a
Scroll methods:   *button
Click methods:    none
Disable-w-typing: n/a
Disable-w-trackpointing: n/a
Accel profiles:   flat *adaptive custom
Rotation:         n/a
```



dConf editor can be used to see parameters set on input devices:
![image](https://github.com/user-attachments/assets/dc328bed-7b86-4b0c-a3bd-7d948ca00c36)
