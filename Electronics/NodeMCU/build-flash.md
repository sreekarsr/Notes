# Building and flashing the firmware

Instructions to build and flash the latest firmware onto the NodeMCU

## Building
- **Cloud build service** ([nodemcu-build](https://nodemcu-build.com))
<br>  Receive the build in your email after selecting the modules you will require.
- **Source build**
<br>[NodeMCU Firmware][firmware] :The source code for building the code on your own. It is recommended to learn this from the [NodeMCU documentation][build-doc] to customize your build.

[firmware]:https://github.com/nodemcu/nodemcu-firmware
[build-doc]:https://nodemcu.readthedocs.io/en/master/build/

## Flashing
1. Download the [flasher](https://github.com/espressif/esptool)
2. Extract and enter the directory and run (if the **cloud build** was used):
```bash
sudo python esptool.py --port /dev/ttyUSB0  write_flash 0x00000 The_Path_To_The_NodeMCU_Firmware.bin`
```
The port name (/dev/ttyUSB0) may sometimes be different. If you are using a **source build**, flash the 0x00000.bin and 0x10000.bin at their corresponding locaitons
```bash
sudo python esptool.py --port /dev/ttyUSB0  write_flash 0x00000 The_Path_To_0x00000.bin 0x10000 The_Path_To_0x10000.bin
```
To erase the existing flashed firmware, use erase_flash.

**(for Windows users)**
- [Random Nerd Tutorials][rand-nerd] - Here's instructions to flash firmware using a GUI for windows

[rand-nerd]:https://randomnerdtutorials.com/flashing-nodemcu-firmware-on-the-esp8266-using-windows/

