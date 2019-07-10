# auto-script-cli

A CLI tool for automating firmware updates and configuration of telecom equipment over serial connections. Built during my studies and used in production to provision AudioCodes Mediant 500 (MSBR) routers.

## How it works

1. Reads work order tickets (local files or network path) to extract provisioning data
2. Generates a configuration script from a template file
3. Connects to the device via serial port (115200 baud)
4. Checks the current firmware version — triggers a TFTP update if outdated
5. Applies the generated configuration script to the device

## Screenshots

![](https://i.imgur.com/1DNWFaE.png)

![](https://i.imgur.com/vwR9rNv.png)

![](https://i.imgur.com/4rmLB6F.png)

![](https://i.imgur.com/U21TkX3.png)

## Requirements

- Python 3
- [pyserial](https://github.com/pyserial/pyserial)
- [PuTTY](https://www.putty.org/) (for manual serial inspection)
- [Tftpd32](http://tftpd32.jounin.net/tftpd32_download.html) (TFTP server for firmware updates)

## Notes

- Developed and tested on Windows — directory paths and serial commands may need adjustment for other operating systems
- The template files and firmware version string can be modified to target different equipment models
