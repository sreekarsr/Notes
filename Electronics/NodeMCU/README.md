# NodeMCU

## Syntax
- [NodeMCU Documentation](https://nodemcu.readthedocs.io/en/master/)
  <br>  A very important read is the [Lua developer FAQ][dev-faq], which stresses on the **event-driven** approach required.
- Lua Syntax - [Programming in Lua](https://www.lua.org/pil/contents.html)

[dev-faq]:https://nodemcu.readthedocs.io/en/master/lua-developer-faq

## Setup instructions
- [Getting Started][get-start] - Clear OS-based descriptions of options available (checkout the matrix) from the official documentation. You may want to use the two pages below to get a brief description. 
- [Building and Flashing](./build-flash.md) the firmware onto your device.
- [Setting up](./uploader.md) your upload tool.

[get-start]:https://nodemcu.readthedocs.io/en/master/getting-started/#getting-started-aka-nodemcu-quick-start

## Tutorials
- [ElectronicWings](http://www.electronicwings.com/nodemcu/basics)
 <br>  A good start covering the basics of using NodeMCU, with descriptions for peripherals. However, do not rely on its details only and use the official documentation for reference, with respect to firmware-building and uploading, as well as code. Certain code snippets are against the _event-driven_ approach that is required to program in when using NodeMCU.
