# REXCPM "UPS"
![](ref/100_3.jpg)
![](ref/100_4.jpg)  
More pics: https://photos.app.goo.gl/i87E4wzimexCR3wL6

System bus interface board for [REXCPM](https://bitchin100.com/wiki/index.php?title=REXCPM) with on-board batteries.

* Provides an on-board battery to preserve the contents of the REXCPM while not installed in a computer, or after the computers memory battery dies, or when the memory power switch is turned off.
* Allows using REXCPM on model 102 without modifying the computer.

REXCPM is a purely volatile SRAM device, which acts like all 3 of RAM, ROM, and DISK. It holds a lot of virtual firmware, rom images, ram image backups, live/working ram, and a disk image for CP/M which holds up to 4 MB of your programs and data, all only in volatile ram.

So this project provides a battery for the REXCPM that does not rely on the host computer.

Even without this auxilliary battery, the REXCPM does have about 15 minutes of memory retention built-in, so the REXCPM can always be disconnected from power at least briefly, to transfer from one machine to another or to change batteries or to turn off the computers memory power switch to force a full hard reset etc.

PCB for Model 100 [PCBWAY](https://www.pcbway.com/project/shareproject/Batteries_for_REXCPM_331c0add.html)  
BOM for Model 100 [DigiKey](https://www.digikey.com/short/21zq7m5n)  

<!-- PCB for TANDY 102 [PCBWAY]()-->  
BOM for Model 102 [DigiKey](https://www.digikey.com/short/7vrw05j1)  

Not in the BOM, you will also optionally need about 2 inches or 50mm of 21-24awg (0.7-0.5mm) insulated solid wire. (solid core ethernet cable is typically 23awg) Thicker is better than thinner. 25mm will be used as a pin that a female dupont connector will go on to. 25mm will be used as mechanical strengthening for one of the battery holders.

PCB ordering notes: If you want the battery terminals to be gold plated, choose ENIG finish when ordering the PCBs. The link above is only for PCBWAY because they have a convenient way to share a pre-loaded link like OSHPark has, except cheaper, faster, and with a fully cleanly cut board outline with no panelization tabs that still need to be sanded down. However PCBWAY is more expensive when you add ENIG. You can take the gerber zip from [releases](../../releases), and both Elecrow and JLCPCB are equivalent quality and speed but don't charge as much extra for ENIG, and OSHPark is always ENIG. OSHPark can also directly accept the kicad_pcb file instead of the gerber zip.

Black versions of the qwiic connector may or may not be available from digikey/mouser etc at any given time, so the BOM has the natural color one. But for reference:  
https://www.sparkfun.com/products/14417  
https://www.adafruit.com/product/4208  

## For TRS-80 Model 100

![](ref/100_1.jpg)
![](ref/100_5.jpg)
![](ref/100_6.jpg)
![](PCB/out/REXCPM_UPS_100.f.jpg)
![](PCB/out/REXCPM_UPS_100.b.jpg)
![](PCB/out/REXCPM_UPS_100.top.jpg)
![](PCB/out/REXCPM_UPS_100.bottom.jpg)
![](PCB/out/REXCPM_UPS_100.svg)

### Assembly Notes

Break the two rear walls off of 3 of the battery holders, so that a battery can pass all the way through the battery holder. The alloy that the battery holders are made of is brittle. When you try to bend the tabs up with pliers, they break off pretty clean right at the bend. Leave one battery holder intact. Install the open holders in BT1-BT3, install the intact holder in BT4.

Optional: There are two exposed vias at the rear of the BT4 footprint. These are for optional added mechanical reinforcenment of the rear walls of the last battery holder, since it takes a fair amount of force to push in all 4 batteries. It's not needed, but you can optionally solder 2 short bits of solid wire from those vias to the rear walls of the battery holder.

After soldering the pins and battery holders, flush-cut everything on the top surface as flush to the pcb as you can, both the dip pins and the battery holders, then add flux and touch each cut post again to reflow them into smooth, flat domes.

## For TANDY Model 102
![](ref/102_1.jpg)
![](ref/102_2.jpg)
![](ref/102_3.jpg)
![](PCB/out/REXCPM_UPS_102.f.jpg)
![](PCB/out/REXCPM_UPS_102.b.jpg)
![](PCB/out/REXCPM_UPS_102.top.jpg)
![](PCB/out/REXCPM_UPS_102.bottom.jpg)
![](PCB/out/REXCPM_UPS_102.svg)

### Assembly Notes

The polarity notch in the 40-pin connector points AWAY from the batteries. The PCB hangs DOWN from the connector when installed on the computer.

After installing the battery holders, flush-cut the solder tabs, add flux to the cut tabs, lay the board battery-side down on the work surface and press down in the center of the pcb with a spudger stick or bamboo skewer, and reflow the cut tabs into smooth flat domes.


## GND Pin Mod

Add a 4th pin to the REXCPM for GND.

This is optional but easy and recommended for longest battery life while the REXCPM is not installed in a computer.

First, warning: While working and handling the REXCPM in general, be very careful not to put any sideways strain on the 3 pins. The vias that the pins are soldered into break free and rotate pretty easily, and breaks the connections to their traces. This has nothing to do with this mod. This can happen any time to any REXCPM, but while doing this work you are more likely to push sideways on the pins than when simply installing the original jumper cable.  
If this happens the situation is still salvagable, you can do the qwiic connector mod below.

Cut a 25mm length of 23awg (0.6mm) solid insulated wire.  
Strip 4mm from one end and bend it 90 degrees.  
Strip 6mm from the the other end.  
Remove the REXCPM from the plastic carrier.  
Insert the straight end of the wire between the large yellow capacitor and the 3 pins (not over top of the cap, it must be to the side and below the top surface of the cap), with the bent end laying on the rear end of the big cap (the end without the stripe, at the rear end of the pcb), and the straight end pointing forward like the 3 pins, but further forward.  
Solder the wire to the capacitor.  

![](ref/gnd_pin_mod_1.jpg)
![](ref/gnd_pin_mod_2.jpg)


## Installation
Connect the 4 female Dupont wires to the REXCPM like this:

BLACK  (GND)     ->  GND pin (the wire you just added, if you did)  
RED    (/WR)     ->  pin closest to cap  
BLUE   (RAM)     ->  middle pin  
YELLOW (RAM_RST) ->  pin furthest from cap

Bend the GND pin slightly away from the other 3 pins so that it doesn't press against them.

If you did not do the gnd pin mod, then just leave the black wire disconnected. 
In this case, the batteries will still retain the REXCPM memory when the computers memory battery dies or the memory switch is turned off, but if the REXCPM is removed from the computer, the memory in the REXCPM may only last a few days. (it may last longer, the time is not known)

While the REXCPM is installed in the computer there is a GND connection between the 2 boards through the computer, and the additional GND wire doesn't make any difference.

While the REXCPM is removed from the computer, there is no proper GND connection between the 2 boards, but there is a backfeed leak via the RAM wire though the NOR chip, and the REXCPM still gets enough power from the batteries to keep the memory alive. However it is not a good connection and the REXCPM memory will not be preserved for as long this way. The exact life time is not known yet, but may be as little as a few days. If you want to be able to remove the REXCPM without counting the hours, you should install the GND pin. If you will leave the REXCPM installed most of the time, and just want the "UPS" to cover when the computers internal battery dies or is turned off, then the extra GND connection isn't strictly needed. You can even still remove the REXCPM, just not for 2 years, but still a lot longer than the 15-20 minutes the capacitor provides.

With 4 new batteries installed and the optional GND wire installed (or with the REXCPM always installed in the computer) then the REXCPM memory should last at least 2 years after the computers internal memory battery dies. This is just an estimate based on measured current drain and the rated capacity of the batteries.

The 4 batteries are connected in parallel. You don't have to install all 4 battery holders and don't have to install all 4 batteries. You can install as little as a single battery. You just get more or less shelf life. Each button cell provides about 6 months of memory retention, estimated. This is in addition to the computers internal battery which can last anywhere from a few weeks to several months. The "clock" on the button cell batteries doesn't start counting until the computers internal memory battery dies.

It's a little tricky to get the batteries back out. The main difficulty is just the spring clip pressure tabs in the holders act like one-way ratchets that allow cells to pass in one direction but can catch on the edge of the cell in the other direction. The simplest way to get the batteries out is just ensure all the cells are touching each other while poking the stack out with a toothpick from BT4. If there is no gap between two cells when they pass under a clip, the clip is more likely to pass from one cell to the next instead of catching. You may still need to wiggle things to cause the cells to tip a little in different directions while pushing out.

![](ref/100_2.jpg)


## Qwiic Mod

This is not really practical because of how tiny the wires and solder points are, but the traces to the original pins on my REXCPM broke so I had to do some sort of repair with bodge wires anyway, so, IF you wanted to and are up to the fine soldering, then here are the connections to install a "qwiic" connector (JST-SH 04 male horizontal smt) onto the REXCPM.

The qwiic connector is one of the black ones like Adafruit or SparkFun has instead of the natural colored ones Digikey and Mouser has,  
https://www.sparkfun.com/products/14417  
to hopefully stick better to the glue. The material feels different and also feels like it has glass filler so it has more texture, especially when scraped with a knife or sanded. I scuffed the bottom surface before gluing.  
The connector is glued bottom-down (pins down, as if soldering to a pcb) on top of one of the 4245 chips with super-glue, with the pins hanging off the edge of the chip in free air. This way the pins are at no risk of touching anything on the pcb, and the cable connector is unobstructed for inserting & removing.

The wire is 30awg wire-wrapping wire. You could use any fine gauge solid insulated wire like winding wire.

The height of the connector ends up exactly the same height as the top of the big capacitor, and does fit under the compartment door.

This is all very tiny to solder correctly, and somewhat fragile when done, the nylon connector housing does pop off the glue if you use any force, and I do not propose this as a convenient practical way to use the battery board for most people.

It does have a few good points though  
* The connection becomes fully polarity protected on both ends. You can disconnect and reconnect later with no risk of wiping out all your data from accidentally connecting the wrong wires even momentarily.  
* The shortest 50mm (2 inch) qwiic cable is usable on Model 100 which is neater and easier than the 150mm dupont breakout cable.  
* The Model 102 connection is better because there are pre-made single-piece 300mm cables.

Cable options for Model 100:  
[SparkFun 17260](https://www.sparkfun.com/products/17260)  
[Adafruit 4399](https://www.adafruit.com/product/4399)  
[Soldered 108342](https://soldered.com/product/easyc-cable-6cm/)  
[JST A04SR04SR30K51A](https://www.digikey.com/en/products/detail/jst-sales-america-inc/A04SR04SR30K51A/6009374) (be careful, there is a cable the looks the same with the same part number except it ends in B instead of A, you need the one that ends in A! The B version swaps the wires along the way. To add to the confusion, the descriptions are backwards, and the A version is described as "reversed", but it reality, the A version does NOT swap the wires (pin 1 goes to pin 1, pin 4 goes to pin 4) while the B version DOES swap the wires (pin 1 goes to pin 4, pin 4 goes to pin 1). You need the A version. This also applies to all the other lengths of the same cable.)

Cable options for Model 102:  
[SparkFun 17257](https://www.sparkfun.com/products/17257) - longer than necessary but available in stock  
[JST A04SR04SR30K305A](https://www.digikey.com/en/products/detail/jst-sales-america-inc/A04SR04SR30K305A/6009382) - would be ideal but not in stock  
[Adafruit 5348](https://www.adafruit.com/product/5384) - not ideal because of the bulky and stiff jacket  
[SparkFun 14429](https://www.sparkfun.com/products/14429) - older version of 17257 with stiffer wire  
Another JST cable [JST A04SR04SR30K305B](https://www.digikey.com/en/products/detail/jst-sales-america-inc/A04SR04SR30K305B/6009394) (same part as above, but last digit is B) is available in stock but the only problem is the pinout is reversed. Since the JST cable wires are not crimped but just IDC (punched into U-shaped blades), it may be possible to peel the wires out of one connector, cut the mangled ends off, and punch them back into the connector in reversed order, perhaps using a spudger. I have not tried so it may not be doable.  

Another option is to keep the [qwiic-to-female cable](https://www.sparkfun.com/products/17261) from the BOM, and add a matching [qwiic-to-male cable](https://www.sparkfun.com/products/17912) to that.

DigiKey and Mouser and other resellers also carry the SparkFun and Adafruit parts, so you can probably get all parts on the same order with the BOM including the cable by searching the part numbers.

![](ref/qwiic_mod_1.jpg)
![](ref/qwiic_mod_2.jpg)
![](ref/qwiic_mod_3.jpg)
![](ref/qwiic_mod_4.jpg)

In Model 100  
![](ref/qwiic_mod_100.jpg)

In Model 102  
![](ref/qwiic_mod_102.jpg)
