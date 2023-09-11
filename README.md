# REXCPM UPS
System bus interface board for [REXCPM](https://bitchin100.com/wiki/index.php?title=REXCPM) with on-board batteries.

## goals  
* battery to keep the REXCPM sram powered while out of the 100 or when the 100's batteries die  
* simpler more convenient standard round pins, simpler to repair  
* more robust all 40 pins instead of delicate single unsupported pins without neighbors  
* more pins -> more friction -> more secure installation  
  also the pins are fatter -> more friction, which is ok in this case because the socket has round pin sockets not flat leaf type  
* parts on bottom in the space created by the tall shoulders of the generic pin headers  
* appearance, pin-1 notch matching the socket, etc

### status
Both versions tested and working, but the batteries don't last long enough to be worth it.

If the REXCPM and bus board are removed from the host computer, there is no proper ground path from the REXCPM back to the bus board to complete the battery circuit. RAM_RST is the positive, and normally the GND connection would be through the GND pins on both the option rom and system bus sockets in the host computer when the REXCPM is installed. But with the REXCPM removed the GND pins are not connected, and so the batteries *shouldn't* actually do anything. But it's working anyway because it's leaking back via that RAM or /WR lines somehow.

With new batteries at 3.2v, and the rexcpm and bus board removed from the 100, the big cap on the rexcpm starts at 4.7v, drains down to 2.5v over 15 minutes, then stays at 2.5v, and then loses another 0.2v over 24 hours. At that rate, the rexcpm memory will only last about 2 to 3 days on it's own.

If the batteries were just powering the sram chip, they should last over a year.

![](ref/100_1.jpg)
![](ref/100_2.jpg)
![](ref/102_200_1.jpg)
![](ref/102_200_2.jpg)

## For TRS-80 Model 100

<!-- PCB [PCBWAY](https://www.pcbway.com/project/shareproject/)  -->
BOM [DigiKey](https://www.digikey.com/short/5zrjvjpw)  

![](PCB/out/REXCPM_UPS_100_f.jpg)
![](PCB/out/REXCPM_UPS_100_b.jpg)
![](PCB/out/REXCPM_UPS_100_b_filled.jpg)
![](PCB/out/REXCPM_UPS_100_batt_end.jpg)
![](PCB/out/REXCPM_UPS_100_wire_end.jpg)
![](PCB/out/REXCPM_UPS_100_top.jpg)
![](PCB/out/REXCPM_UPS_100_bottom.jpg)
![](PCB/out/REXCPM_UPS_100.svg)

## For TANDY Model 102 and 200

<!-- PCB [PCBWAY](https://www.pcbway.com/project/shareproject/)  -->
BOM [DigiKey](https://www.digikey.com/short/90wmmfhv)  

![](PCB/out/REXCPM_UPS_102_200_f.jpg)
![](PCB/out/REXCPM_UPS_102_200_b.jpg)
![](PCB/out/REXCPM_UPS_102_200_top.jpg)
![](PCB/out/REXCPM_UPS_102_200_bottom.jpg)
![](PCB/out/REXCPM_UPS_102_200.svg)
