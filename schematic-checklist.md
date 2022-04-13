# Schematic review checklist

## 1 Document Setup
* [ ] 1.1 Is there a method for tracking versions/revisions?	
* [ ] 1.2 Is source version control used? (Git, SVN, etc.)

1.3 Are design decisions well documented?	
- * [ ] 1.3.1 Within or separate from the schematic/drawings?	\n\n
* [ ] 1.4 Has ERC been set up and configured?	
* [ ] 1.5 Has grid size been selected?	
* [ ] 1.6 Has paper sizes been selected for sheets?	


## 2 Schematic
### 2.1 Symbols
- * [ ] 2.1.1 Are explicit and informative	
- * [ ] 2.1.2 Do they resemble electrical circuit symbols?
- * [ ] 2.1.3 Reflect the functionality or logical structure of the component?	
- * [ ] 2.1.4 Pins are assigned the correct type (passive, power in, out, etc.)?	
- * [ ] 2.1.5 Pin numbers are identical to datasheet or external interface specification document	
- * [ ] 2.1.6 Are active-high and active-low marked consistently?	
- * [ ] 2.1.7 Do pin positions adhere to the selected grid size?	
- * [ ] 2.1.8 Do symbols match chosen component package?	
- * [ ] 2.1.9 Are datasheets included with each symbol?	
### 2.2 Functionality
#### 2.2.1 Are all pins on all ICs handled?	
- * [ ] 2.2.1.1 Beak-out of extra pins from ICs or subsystems?	
- * [ ] 2.2.2 Are mating connectors on different boards matched in pin-out?	
- * [ ] 2.2.3 Have necessary inputs been ESD protected?	
- * [ ] 2.2.4 Multipart components are identified and utilized	
### 2.3 Electrical
#### 2.3.1 Power Supply
##### 2.3.1.1 System Power Input
- * [ ] 2.3.1.1.a Are fuses and/or reverse voltage protection at system power inlet?	
- * [ ] 2.3.1.1.b Check total input capacitance and add inrush limiter if needed
##### 2.3.1.1 Regulators
- * [ ] 2.3.1.2.a Is under/overvoltage protection configured correctly if used	
- * [ ] 2.3.1.2.b  Verify estimated power usage per rail against regulator rating
- * [ ] 2.3.1.2.c  Are current-sense resistors on power rails after regulator output caps, not in switching loop	
- * [ ] 2.3.1.2.d  is remote sense used on low voltage or high current rails	
- * [ ] 2.3.1.2.e  Linear regulators and voltage reference ICs are stable with selected output cap ESR	
- * [ ] 2.3.1.2.f  Confirm power rail sequencing against device datasheets
##### 2.3.1.3 Decoupling
- * [ ] 2.3.1.3.a Decoupling present of all ICs	
- * [ ] 2.3.1.3.b Decoupling meets/exceeds vendor recommendations if specified	
- * [ ] 2.3.1.3.c Bulk decoupling present at PSU	
##### 2.3.1.4 General
- * [ ] 2.3.1.4.a All power inputs fed by correct voltage
- * [ ] 2.3.1.4.b Check high-power discrete semiconductors and passives to confirm they can handle expected load
- * [ ] 2.3.1.4.c Analogue rails filtered/isolated from digital circuitry as needed
- * [ ] 2.3.1.4.d Are polarized components protected/ensured from/against reverse voltage?
- * [ ] 2.3.1.4.e Are resistors operating within their specified voltage/power range?
- * [ ] 2.3.1.4.f Is a low-impedance source driving tantalum capacitors?
#### 2.3.2 Signals
##### 2.3.2.1 Digital
- * [ ] 2.3.2.1.a Signals are correct logic level for input pin	
- * [ ] 2.3.2.1.b Pullups are on all open-drain outlets	
- * [ ] 2.3.2.1.c Pulldowns are on all PECL outputs	
- * [ ] 2.3.2.1.d Are reset pins pulled high/low?	
- * [ ] 2.3.2.1.e Termination on all high-speed signals	
- * [ ] 2.3.2.1.f AC coupling caps on gigabit transceivers	
- * [ ] 2.3.2.1.g TX/RX paired correctly for UART, SPI, MGT, etc.	
- * [ ] 2.3.2.1.h Differential pair polarity/pairing correct	
- * [ ] 2.3.2.1.i Active high/low enable signal polarity correct	
- * [ ] 2.3.2.1.j I/O banking rules met on FPGA etc.	
- * [ ] 2.3.2.1.k When using auto-sensing level shifters, ensure the intended receiver doesn't have a pullup/pulldown	
##### 2.3.2.2 Analogue
- * [ ] 2.3.2.2.a RC time constant attenuators sane given ADC sampling frequency	
- * [ ] 2.3.2.2.b  Verify frequency response of RF components across entire operating range. Don't assume a "1-100 MHz" amplifier has the same gain across the whole range.	
- * [ ] 2.3.2.2.c Verify polarity of op-amp feedback	
##### 2.3.2.3 Clocks
- * [ ] 2.3.2.3.a All oscillators meet required jitter/frequency tolerance. Be extra cautious with MEMS oscillators as these tend to have higher jitter	
- * [ ] 2.3.2.3.b Correct load caps provided for discrete crystals	
- * [ ] 2.3.2.3.c Crystals only used if IC has integrated crystal driver
##### 2.3.2.4 Strap/init pins
- * [ ] 2.3.2.4.a Pullup/pulldowns on all signals that need defined state at boot	
- * [ ] 2.3.2.4.b Strap pins connected to correct rail for desired state	
- * [ ] 2.3.2.4.c JTAG/ICSP connector provided for all programmable devices	
- * [ ] 2.3.2.4.d Config/boot flash provided for all FPGAs or MPUs without internal flash	
- * [ ] 2.3.2.4.e Reference resistors correct value and reference rail	
##### 2.3.2.5 External interface protection
- * [ ] 2.3.2.5.a Power outputs (USB etc.) current limited	
- * [ ] 2.3.2.5.b ESD protection on data lines going off board
##### 2.3.2.6 Debugging/reworking
- * [ ] 2.3.2.6.a Use 0-ohm resistors vs direct hard-wiring for strap pins when possible	
- * [ ] 2.3.2.6.b Provide multiple ground clips/points for scope probes	
- * [ ] 2.3.2.6.c Dedicated ground in close proximity to analogue test points 	
- * [ ] 2.3.2.6.d Test points on all power rails	
- * [ ] 2.3.2.6.e Test points on intersecting signals which may need probing for bringup/debug
### 2.4 Thermal
- * [ ] 2.4.1 Power estimates for all large / high power ICs	
- * [ ] 2.4.2 Thermal calculations for all large / high power ICs	
- * [ ] 2.4.3 Specify heatsinks as needed	
