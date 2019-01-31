# MX4N

A brave effort to make a flashable linux image for the MX4N (8G1/1G) board fouund in the SCISHION V88 Android TV box


MX4N 8G/1G


- CPU : Rockchip RK3229 quad core ARM Cortex A7 processor @1.5 GHz
- GPU : ARM Mali-400MP
- Memory : 1GB DDR3
- Storage : 8GB NAND flash + SD card slot up to 16GB
- Video Output : HDMI 2.0 up to 4K2K @60 fps, and 3.5mm AV output (composite)
- Audio Output : HDMI, AV, and coaxial S/PDIF
- Connectivity : 100Mbps Ethernet, 802.11 b/g/n WiFi
- USB : 4x USB 2.0 host ports
- Interfaces : HDMI port, RJ45 port, SPDIF port, 4x USB Host, SD Card Slot, AV Out DC jack.
- Power Supply : 5V/2A

## TODO
- [x] get UART output through SDcard slot
- [ ] Build own U-Boot / Kernel / rootfs
- [ ] Video Output while booting
- [ ] Enable UART routing to USB port(?)
- [ ] Enable netbooting
