# ACORP-S100L-Ethernet-Card-WOL-Mod
Easy hardware mod enables Wake on LAN support in acorp-s100l ethernet card
## Modification
Things Required:
- 15k ohm resistor SMD, 1 Piece
- Any rectifier diode like 1N4001/1N4007 or SMD, 1 Piece

Photo before changes

![image](https://github.com/Zer0Notha/ACORP-S100L-Ethernet-Card-WOL-Mod/blob/master/images/1.jpg)

After

![image](https://github.com/Zer0Notha/ACORP-S100L-Ethernet-Card-WOL-Mod/blob/master/images/2.jpg)

## Explanation of what's going on

Any RTL8139D or RTL8139C based ethernet card can include WOL function itself because WOL realized by hardware in RTL, but some manufacturers do not bother to add this feature.
So we can correct this situation by following some steps:
- Locate RTL Power node what connected to PCI +5V through diode
- Locate A14 PCI Pin
- Provide power supply when motherboard in off/sleep state by soldering diode between RTL Power node and A14 PCI Pin
- Notify RTL about external power supply by soldering ~15kOhm resistor between AUX RTL Pin and A14 PCI Pin
- Make sure that when PCI power down ISOLATEB Pin is not powered up (This isolates PCI bus from RTL when the motherboard is powered down)

![image](https://github.com/Zer0Notha/ACORP-S100L-Ethernet-Card-WOL-Mod/blob/master/images/3.png)
