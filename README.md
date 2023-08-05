# ARCHIVED

This project is not being worked on anymore. A new, linux-only version is being developed [here.](https://github.com/Fushko/gummy)

# Gammy
is a tool for adjusting pixel brightness/temperature automatically or manually.

It can dim the screen if its content is too bright, or brighten it otherwise. This can help your eyes adjust when switching between dark and light windows, especially at night or in suboptimal lighting conditions.

Screenshot available on its [website](https://getgammy.com).
#### Planned features

- Proper multi-monitor support
- Command line interface / configurable hotkeys
- Location-based temperature adaptation
- Backlight control
## Installation

### Linux
### Building from source
Requirements:
- g++ or Clang compiler with C++17 support
- Ubuntu/Debian packages:
```sh
sudo apt install build-essential libgl1-mesa-dev libxxf86vm-dev libxext-dev qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools
```
To install:
```sh
git clone https://github.com/Fushko/gammy.git
cd gammy
qmake
make
sudo make install
```
You can then find Gammy in your applications.
To run it from the shell, execute: `gammy`

To uninstall:
```sh
sudo make uninstall
```
On GNOME, the Qt5 Configuration Tool is recommended to improve UI integration:
```sh
sudo apt install qt5ct
```

## Known issues and limitations
The brightness is adjusted by changing pixel values, instead of the LCD backlight. This has wildly varying results based on the quality of your screen.

Theoretically, this app looks best on OLEDs, since they don't have a backlight. (If you have one, I'd love to know your experience).

Backlight control is planned. However, not all screens support backlight control via software.

### Multi-monitor issues
On Windows, currently the brightness is detected and adjustable only on the monitor that is set as the primary screen. Temperature affects all screens, however.

On Linux, currently every screen is treated as one single screen when calculating brightness. Both brightness and temperature are changed globally.

## Third party
- Qt 5 ([LGPL](https://doc.qt.io/qt-5/lgpl.html))
- Plog ([MPL](https://github.com/SergiusTheBest/plog/blob/master/LICENSE))
- JSON for Modern C++ ([MIT](https://github.com/nlohmann/json/blob/develop/LICENSE.MIT))
- Qt-RangeSlider ([MIT](https://github.com/ThisIsClark/Qt-RangeSlider/blob/master/LICENSE))

## License
Copyright (C) Francesco Fusco.

[GPLv3](https://github.com/Fushko/gammy/blob/master/LICENSE)

