# TuKVM Hardware

TuKVM is a hardware project that aims to provide a simple but feature rich IP KVM solution. The project is based on the [Tronlong SOM-TLT113](https://www.tronlong.com/Product/show/237.html) SoM, which includes an Allwinner T113-i SoC, with dual-core Cortex-A7 CPU, 256MB DDR3 RAM, and 4GB eMMC.

![PCB render image](https://raw.githubusercontent.com/gaoyichuan/tukvm-hardware/main/images/pcb-front-render.jpg)

## Features

* PCIe x1 half-height form factor, with breakable edge connector for mounting in systems without free slots
* HDMI input capture (up to 1080P30) with [MS2109](http://en.macrosilicon.com/info.asp?base_id=2&third_id=50) IC
* ATX power / reset button control with opto-isolator
* Power and HDD LED monitoring with opto-isolator
* 9 pin 2.54mm internal USB OTG port for mass-storage, keyboard, mouse emulation and Ethernet-over-USB
* USB-C external power input and UART console port for debugging
* 100Mbps Ethernet with [LAN8720A](https://www.microchip.com/en-us/product/lan8720a) PHY
* RS232 serial port with 2.54mm header for host system console redirection
* SMBus on PCIe connector for Linux kernel to recongnize the KVM as an IPMI device, using [ipmi_ssif](https://github.com/torvalds/linux/blob/master/drivers/char/ipmi/ipmi_ssif.c) driver
* (Optional) Isolated 802.3af PoE input with [DP1435-5V](https://item.szlcsc.com/6245786.html) controller module
  

## Status

This project is currently in the prototyping phase. The hardware design is mostly complete, and the first prototype PCBs have been ordered. 

The firmware and software development isn't started yet, but the plan is to port [kvmd](https://github.com/pikvm/kvmd) from PiKVM project to the Allwinner T113-i SoC. Support for SMBus and IPMI protocol will need extra driver and software development. Any help is welcome!

## License

This project is licensed under the CERN Open Hardware License v2 - Permissive license. See the [LICENSE](LICENSE) file for details.
