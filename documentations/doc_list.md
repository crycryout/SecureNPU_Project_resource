### Zhengdianyuanzi Resources (including source code, system image, reference manual, compiling tools, VM tools, etc.):

* [Zhengdianyuanzi Documentation](http://www.openedv.com/docs/boards/arm-linux/iMX93.html)

### NXP Resources:

* **Source Code/Image**: You can build the source code from here, but the development board may not be fully compatible.
  * [NXP Embedded Linux for i.MX Applications Processors](https://www.nxp.com/design/design-center/software/embedded-software/i-mx-software/embedded-linux-for-i-mx-applications-processors:IMXLINUX)

### Debugging Cortex-M and Writing Code for Cortex-M (J-Link required; otherwise, it will show "no probe detected"):

* **MCUXpresso for VS Code**: Do not use MCUXpresso IDE, as it doesn't support i.MX93.
  * [MCUXpresso Software and Tools](https://www.nxp.com/design/design-center/software/development-software/mcuxpresso-software-and-tools-:MCUXPRESSO)
  * Note: When running the MCUXpresso installer, be patient. The installation of the ARM compiler will require a long time, and if you rerun it, it might miss some libraries after finishing, rendering it unusable. VS Code will indicate that it can't resolve the dependency and will switch to other compilers, which may not work.

### Debugging Cortex-M While Cortex-A is Running (We must debug Cortex-M while Cortex-A is running; this document shows how to load firmware to M through Linux running on A):

* [AN14120: Debugging Cortex-M with VS Code on i.MX 8M, i.MX 8ULP, and i.MX 93](https://www.nxp.com/docs/en/application-note/AN14120.pdf)

### Obtaining and Building the Source Code (The built firmware may not fit the board well and may require further modification):

* [AN13854: NPU Migration Guide from i.MX 8M Plus to i.MX 93](https://www.nxp.com/docs/en/application-note/AN13854.pdf)

### Useful Book on Embedded Security, Including TrustZone M:

* [Embedded Systems Security and TrustZone](https://embeddedsecurity.io/)

### NXP Community (Ask questions if you get stuck; NXP TechSupport might reply in days):

* [NXP Community](https://community.nxp.com/)

### i.MX Software:

* [NXP i.MX GitHub](https://github.com/nxp-imx)

### Trusted Firmware:

* [Trusted Firmware](https://www.trustedfirmware.org/)
  * You can find TF-A, TF-M, OP-TEE, and other trusted software codes/documentations here.

### TEE Overview & Quick Start:

* [The Linux Foundation YouTube Channel](https://www.youtube.com/@LinuxfoundationOrg)
  * Can find many useful videos here.
* [Linaro YouTube Channel](https://www.youtube.com/@LinaroOrg)
* [Pengutronix YouTube Channel](https://www.youtube.com/@Pengutronix)
