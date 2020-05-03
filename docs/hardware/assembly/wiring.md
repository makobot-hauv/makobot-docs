# Wiring Modifications


## Ethernet Wiring

The camera modules and the port and starboard modules are connected via Ethernet through 8-pin Teledyne bulkhead connectors.

The housings have a female 8-pin bulkhead (Teledyne connector number MCBH-8-FS) and the cables between housings are male 8-pin inline connectors (Teledyne connector MCIL-8-MP) on 2 feet of Belden cable.

IMPORTANT NOTE: These Belden cables are not actually rated for ethernet and do not contain twisted pairs. The cables are currently only 2 ft long and we have been observing adequate speeds (limited to 100BASE-T) over these cables, but this could be an issue in the future, especially if increased data speeds (e.g. gigabit) are needed. Cables would need to be replaced with a ProPlex PCCAT5EP or similar cable. Revisit this later if it become an issue.

TODO: speed benchmarking across current Teledyne Ethernet cables

### Belden Cable Wiring

The table below shows the mapping from bulkhead pin number to Belden cable wire color.

| Bulkhead Pin # | Belden Cable Wire Color |   
|---|-------|
| 1 |  black  |
| 2 |  white  |
| 3 |  red  |
| 4 |  green  |
| 5 |  blue  |
| 6 |  brown  |
| 7 |  yellow |
| 8 |  orange  |

![teledyne pin numbering](https://raw.githubusercontent.com/makobot-hauv/makobot-docs/master/img/bulkhead_8pin_diagram.png)

Each pin number corresponds directly to the number on the punchdown connector (TODO add diagram). I.e., pin 8/orange wire will be wired to pin 8 on the punchdown.

The bulkhead connectors use the same convention as the cables for wiring to the punchdown connectors. That is, pin 1/wire 1 on the bulkhead connector will wire to pin 1 on the punchdown connector, etc. Labels 1-8 on the internal white wires on the connectors correspond directly to the pin numbers on the outer bulkhead.

### Tether Ethernet Wiring

The coloring on the tether pairs is different than on the Teledyne cable interconnects. The robot tether pairs are mapped to the punchdown connectors as follows:

| orange / white | green / white | blue / white | brown / white |
| -------------- | ------------- | ------------ | ------------- |
|   2   /   1    |   6   /   3   |   4  /   5   |   8   /   7   |  
