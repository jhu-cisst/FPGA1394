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
* Rev 1.3: Build #4 (80 boards)
 * Added protection diodes (D10-D17), shunt regulator (U12), and supporting components to FireWire signal lines
 * Enable off-board 5V and 3.3V power (via U4 and U5) after local 5V power is good (determined by U9)
 * Added holes/pads on PCB traces for 5V, 3.3V, and 1.2V power supplies to facilitate troubleshooting
 * Removed 29.4989 MHz oscillator (U12) and supporting components from PCB and BOM (was "Do Not Install")
 * Modified U2 footprint to accommodate all variants of SO-8 package
 * Changed internal layers from 2 oz to 1 oz copper
* Rev 2.0: Prototype build (3 boards)
 * Added 10BASE-T/100BASE-TX Ethernet port using Micrel KSZ8851-16MLL MAC/PHY chip.
 * Redesigned DC/DC power supplies (5V, 3.3V, and 1.2V) to provide higher output currents.
 * Removed USB Mini connector (J6) and associated USB to UART bridge chip (CP2103). It is still possible to obtain a USB interface by connecting an appropriate TTL to USB Serial Converter Cable to header J9.
 * Removed jumper (J10) that allowed board to obtain power from IEEE-1394 cable (this feature was never used). Also removed power passthrough between IEEE-1394 connectors.
 * Removed diode isolation between power supply connectors J5 and J7; power should be connected to only one of these.
 * Changed FPGA oscillator from 40 MHz (pin AB12) to 25 MHz (pin M3).
 * Changes to the I/O pin connections on the FPGA (see schematic).
* Rev 2.1: Build #5
 * Moved power connector (J5) to make more space for JTAG connector (J8).
 * Corrected connection of "ST" and "FPGA PROG" LEDs (were swapped in Rev 2.0).
 * Fixed one unconnected GND test point, moved voltage test points, and added GND test point.
 * Changes to facilitate board assembly: wider slot spacing for IEEE-1394 connector, notch on board edge for better seating of IEEE-1394 connector, changed pad size for L1-L3 to match manufacturer datasheet.
