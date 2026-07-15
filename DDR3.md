https://discordapp.com/channels/694859291680702495/708982365816487998/1526970004464074882
```
Here you go.  Application notes, design guides, component datasheets to get you started on DDR3 memory.
I am still learning ddr myself. I got these from Phillip Salmony's  Advanced Digital Hardware Design course on Fedevel Academy.

https://hands.com/~lkcl/eoma/rockchip_rk3288/AN3940.pdf
https://docs.amd.com/v/u/en-US/ug933-Zynq-7000-PCB
https://www.mouser.de/datasheet/2/671/4Gb_DDR3L-1283964.pdf
https://fscdn.rohm.com/en/products/databook/datasheet/ic/power/linear_regulator/bd3539xxx-e.pdf
```
https://discordapp.com/channels/694859291680702495/708982365816487998/1526971276885753908
```
Having designed with DDR3 myself, the Zynq SoC stuff is fairly well put together. This document from TI is also pretty good. https://www.ti.com/lit/an/sprabi1d/sprabi1d.pdf?ts=1784073054555

A couple things of note, firstly, the routing for DDR isn't really that special. Just impedance matching, some (relatively generous unless you're going quite fast) length matching, and basic SI stuff like don't fuck up return paths or pack your traces in super tight for long parallel stretches. One thing to watch out for, on typical SDRAM you can swap around the data and address pins to make routing more convenient, since nothing cares if the address 0010 from the host gets read as 0100 instead as long as it's consistent. On DDR ram, the address pins are used for config on boot and cannot be swapped, so A0 on the host must be A0 on the ram, etc. That said, within your byte groups on the data bus you can swap around however you please to make routing easier.
```