# Building and flashing the firmware

Instructions to build and flash the latest firmware onto the NodeMCU

## Building
- **Cloud build service** ([nodemcu-build](www.nodemcu-build.com))
<br>  Receive the build in your email after selecting the modules you will require.
- **Source build**
<br> Download the [firmware] and follow the instrucitons as on the [documentation][flash-doc]

[firmware]:https://github.com/nodemcu/nodemcu-firmware
[flash-doc]:https://nodemcu.readthedocs.io/en/master/flash/

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
