# Rasbperry Pi

## WiFi

**Scanning for networks** List all details of available networks. (look for ESSID)
```bash
sudo iwlist wlan0 scan
```
**Enter ssid and password in the configuration file**
Open it 
```bash
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```
then change ssid, psk, (country if its wrong), then exit and save with Ctrl+X

**Checking which network currently connected to** Use `iwget` to display the SSID.
`iwconfig` can also give a lot of details
**checking ip address** 
```bash
hostname -I
```
**Troubleshooting**
Try restarting wireless connectivity if it doesn't start
```bash
sudo ifdown wlan0
sudo ifup wlan0
``` 
Basic WiFi setup can be done using raspi-config  but is not as straightforward

Sources: [makeuseof],[stackexchange][stkwifi]
Pretty comprehensive(for other details) : [stackexchange Wifi detailed post][stkwifid]


[makeuseof]:https://www.makeuseof.com/tag/setup-wi-fi-bluetooth-raspberry-pi-3/
[stkwifi]:https://raspberrypi.stackexchange.com/questions/41020/how-do-i-use-the-command-line-to-check-which-wifi-network-i-am-connected-to
[stkwifid]:https://raspberrypi.stackexchange.com/questions/37920/how-do-i-set-up-networking-wifi-static-ip-address/37921#37921

## Using a camera
- [Using a webcam][webcams] with the raspberry pi
- [Using the official RPi camera module][rpicam] - (said to have more quality and configurability)

[rpicam]:https://www.makeuseof.com/tag/set-up-raspberry-pi-camera-module/
[webcams]:https://www.raspberrypi.org/documentation/usage/webcams/

## General
```bash
sudo apt update
sudo apt upgrade
```
**Getting ip address of RPi**
```bash
cat /var/lib/misc/dnsmasq.leases
```
**Checking the OS release**
```bash
cat etc/os-release
```

**Shutting down**
```bash
sudo shutdown -h now
```
or 
```bash
sudo halt
```
**Reset username and password without KB/mouse **
Source : [stackexchange]

[stackexchange]:https://raspberrypi.stackexchange.com/questions/24770/change-reset-password-without-monitor-keyboard

