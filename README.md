# MX4N

A brave effort to make a flashable linux image for the MX4N-V20 (8G1/1G) board found in the SCISHION V88 Android TV box

:warning: WARNING :warning:
```
 Experimental stuff going on here, proceed with caution! 
```


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

# How-to UART

###### What you need
- USB A Male to Male adapter
- Empty microSD adatper
- 3x Breadboard wires


###### Wiring
SDslot pinout seen from back of slot
```
 9   1   2   3   4   5   6   7   8
[ ] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [ ]
```

USB-TTL and SDslot wiring

```
USB-TTL     SDslot
  RXD   ->    7
  TXD   ->    2
  GND   ->   GND
```
Insert the microSD adapter halfway and get the breaboard wires into the back of SDslot [See picture](docs/PICTURES.md) and connect
them to the USB-TTL adapter

Connect USB-TTL and open terminal emulator of choice
```
Baudraute : 1.5M (1500000)
Data bits : 8
Stop bits : 1
```
Insert USB A Male to Male adapter into the OTG usb port (USB-4) and you should see lots of [text](/uart_output.txt) scrolling in your terminal window (rejoice!) :thumbsup:


# How-to Build U-Boot

Follow this guide

or..

One [script](scripts/README.md) to handle it all



## How to flash new u-boot.img to board



## How-To boot the new u-boot.img from SD

# How to..

## How-to recover

- Start AndroidTool/RKBatchTool
- Shorten pins 8 & 9 on the nand chip (see image and make sure you do this right!!!)
- Power up using the OTG port

You should now see 'Found One MASKROM Device'

- Click the 'Upgrade Firmware' tab, then 'EraseFlash' (i had to select firmware before erasing)
- If successful, hit the 'Upgrade' button

All good?

## Repair corrupted SDcard..
Red LED after tampering with the files on SDcard? 
```
sudo fdisk -l
sudo fsck -a /dev/sd[partition] 
```
###### 
