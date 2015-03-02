# FPGA1394
Design files for FPGA1394 board (FPGA + FireWire) in Altium Designer format.

* `FPGA.PrjPCB`: Altium Designer project file
* `Snn.SchDoc`: schematics (Altium Designer format)
* `FPGA.PcbDoc`: PCB layout (Altium Designer format)
* `FPGA-Schematics.pdf`: PDF of schematics
* `FPGA-BOM.xls`: Bill of Materials (Microsoft Excel format)
* `FPGA1394-PCB-Fabrication.zip`: PCB fabrication (Gerber) files
* `FPGA1394-Assembly.zip`: PCB assembly files (e.g., paste masks, pick-and-place)
 
## Release Notes
 
* Rev 1.0/1.1 (PCB silkscreen is 1.0): Build #0 (5 board pilot run), Build #1 (44 boards)
* Rev 1.2: Build #2 (68 boards), Build #3 (72 boards)
 * Added J10 jumper on power input from IEEE-1394 (jumper OFF -> no power from IEEE-1394)
 * Changed J9 from 4-pin 2 mm header to 5-pin 0.1" header; pin 5 is connected to GND
 * Did not populate U12 (29.4989 MHz oscillator); use FPGA PLL to generate this frequency
* Rev 1.3: Build #4
 * Added protection diodes (D10-D17), shunt regulator (U12), and supporting components to FireWire signal lines
 * Enable off-board 5V and 3.3V power (via U4 and U5) after local 5V power is good (determined by U9)
 * Added holes/pads on PCB traces for 5V, 3.3V, and 1.2V power supplies to facilitate troubleshooting
 * Removed 29.4989 MHz oscillator (U12) and supporting components from PCB and BOM (was "Do Not Install")
 * Modified U2 footprint to accommodate all variants of SO-8 package
 * Changed internal layers from 2 oz to 1 oz copper
