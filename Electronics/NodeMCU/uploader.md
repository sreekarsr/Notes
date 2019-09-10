# Upload tools
## NodeMCU-Tool
A very well-maintained command line-tool which is arguably better than the other options for interacting with your NodeMCU.
- [NodeMCU-Tool] source
- [Quick start instructions][instr] from NodeMCU documentation

[NodeMCU-Tool]:https://github.com/andidittrich/NodeMCU-Tool
[instr]:https://nodemcu.readthedocs.io/en/master/getting-started/#nodemcu-tool

## ESPlorer
If you're not a fan of the CLI, ESPlorer is a GUI to program ESPs in Lua
1. [Download][dwld-link] the zip file and extract it.

[dwld-link]:http://esp8266.ru/esplorer-latest/?f=ESPlorer.zip

2. Then enter the directory and run `java -jar ESPlorer.jar`. You may lock ESPlorer onto your Ubuntu launcher for convenience.

## Arduino
Using the Arduino IDE is possible, but the uploading of code takes too long(as arduino also uploads its own firmware onto it), and it's not the way (IMO) NodeMCU was meant to be used.
This becomes a departure from the event-driven approach possible in Lua. Details may be found, if required on [ElectronicWings](https://www.electronicwings.com/nodemcu/arduino-ide).

[Back](./README.md)
