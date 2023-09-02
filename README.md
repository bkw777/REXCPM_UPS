# REXCPM UPS
A replacement Model 100 system bus board for REXCPM with on-board batteries.

## goals  
* battery to keep the REXCPM sram powered while out of the 100 or when the 100's batteries die  
* simpler more convenient standard round pins, simpler to repair  
* more robust all 40 pins instead of delicate single unsupported pins without neighbors  
* more pins -> more friction -> more secure installation  
  also the pins are fatter, which is ok in this case because the socket has round sockets not flat leaf type  
* parts on bottom in the space created by the tall shoulders of the standard pins  
* lower profile so that the board no longer pushes up on the compartment cover (the main REXCPM module needs this too but will not be so easy)  
* looks, board outline with pin-1 notch matching the socket  

<!-- better while on github, broken everywhere else -->
<!-- ![](../../raw/main/PCB/out/REXCPM_UPS_f.jpg -->

![](PCB/out/REXCPM_UPS_f.jpg)
![](PCB/out/REXCPM_UPS_b.jpg)
![](PCB/out/REXCPM_UPS_b_filled.jpg)
![](PCB/out/REXCPM_UPS_end_b.jpg)

Single cell option. Just install one battery holder. You can use either position, they are connected in parallel. So if you prefer the battery be more recessed and protected, you cane use just the BT2 position instead of BT1.  
![](PCB/out/REXCPM_UPS_1_batt.jpg)

Two-cell option. Bend up the rear wall tabs on one of the holders, and pass the 2nd cell through the BT1 holder.
![](PCB/out/REXCPM_UPS_2_batt.jpg)

## schematic & pcb

![](PCB/out/REXCPM_UPS.svg)
![](PCB/out/REXCPM_UPS_top.jpg)
![](PCB/out/REXCPM_UPS_bottom.jpg)

(No pcb fab link until the design is actually tested)
<!--
PCB [PCBWAY](https://www.pcbway.com/project/shareproject/)  
BOM [DigiKey](https://www.digikey.com/short/)
-->
