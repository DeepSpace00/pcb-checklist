# Layout review checklist

* [ ] [Schematic review](schematic-checklist.md) complete and signed off, including pin swaps done during layout

## 1 Document Setup
* [ ] 1.1 Is there a method for tracking versions/revisions?	
* [ ] 1.2 Is source version control used (Git, SVN, etc.)?	
* [ ] 1.3 Are design decisions well documented?	
* [ ] 1.4 Has DRC been set up and configured?	
* [ ] 1.5 Has grid size been selected?	
## 2 Manufacturing
### 2.1 General
- * [ ] 2.1.1 Are gold fingers needed?	
- * [ ] 2.1.2 Is there a bill of materials?	
- * [ ] 2.1.3 Are solder paste openings the correct size?	
### 2.2 Panelization
- * [ ] 2.2.1 Do layers line up with panalized files	
- * [ ] 2.2.2 Is the stack-up correct	
- * [ ] 2.2.3 Fits test rig	
- * [ ] 2.2.4 Panel location indicators for identifying location-specific reflow issues	
### 2.3 Assembly
- * [ ] 2.3.1 Is there enough space for the minimum bending radius of the wire harnessing?	
#### 2.3.2 Are fiducials needed for assembly?	
- * [ ] 2.3.2.1 Are fiducials asymmetric to detect if board is upside down?	
* [ ] 2.3.3 Is there a necessary order for mounting components on the board?
* [ ] 2.3.4 Will mounting certain components make it impossible to mount others	
* [ ] 2.3.5 Is there an assembly order for subsystems?	
* [ ] 2.3.6 Is there a testing order for subsystems?
## 3 Footprints
* [ ] 3.1 Is Pin 1 Marked in a consistent manner?	
### 3.2 Is component polarity marked in a consistent manner?
- * [ ] 3.2.1 For electrically polarized components like capacitors and diodes?	
- * [ ] 3.2.2 For keyed components like connectors?	
* [ ] 3.3 Are high-density chips marked with pin numbers?	
* [ ] 3.4 Are there tick-marks every 5-10 pins on high pin count chips?	
* [ ] 3.5 Are there square pins for pin 1 on components? Are the holes big enough?	
* [ ] 3.6 Have the footprint dimensions been cross-checked with recommended footprints for the specific component?	
* [ ] 3.7 Are the footprints from the datasheet defined as top view or bottom view?	
* [ ] 3.8 Confirm components are available in selected package?	
* [ ] 3.9 Confirm components and connectors are capable of desired current in the selected package	
* [ ] 3.10 Verify schematic symbol matches the selected package	
* [ ] 3.11 Download and view 3D model (if available) and check against footprint	
## 4 Placement
* [ ] 4.1 Are jumpers accessible? 	
* [ ] 4.2 Are debug connectors accessible?	
* [ ] 4.3 Are filter resistors closer to the source?	
* [ ] 4.4 Are decoupling capacitors close to the chip?	
* [ ] 4.5 Are termination resistors closer to the target?	
## 5 Clearance
* [ ] 5.1 Are all keep-out areas honored?	
* [ ] 5.2 Around mounting holes?	
* [ ] 5.3 For IC extraction tools?	
* [ ] 5.4 For programming tools?	
* [ ] 5.5 For assembly tools?	
* [ ] 5.6 For for probes?	 
* [ ] 5.7 Trace-to-trace clearance based upon voltage rating
## 6 Mechanical
* [ ] 6.1 Is there spacing for an assembly run marking?
* [ ] 6.2 Is there clearance for connectors (such as microSD modules and BGA uCs? looking at you Arsenio 👀)
* [ ] 6.3 Are there mounting holes?
* [ ] 6.4 Should mounting holes be electrically isolated?	 
* [ ] 6.5 Should grounded mounting holes have via stitching?	 
* [ ] 6.6 Are hole diameters compensating for plating?	 
* [ ] 6.7 Is the outline of the board defined?	 
* [ ] 6.8 Is there enough space for mating connectors?	 
* [ ] 6.9 Is there enough vertical space for components?	 
* [ ] 6.10 Is there a drill legend?	 
* [ ] 6.11 Are internal corners rounded? can they be milled?	
* [ ] 6.12 Confirm all connectors to other systems comply with the appropriate mechanical standard (connector orientation, key position, etc)	 
* [ ] 6.13  LEDs, buttons, and other UI elements on outward-facing side of board	 
* [ ] 6.14  Keep-outs around PCB perimeter, card guides, panelization mouse-bites, etc respected	 
* [ ] 6.15  Stress-sensitive components (MLCC) sufficiently clear from V-score or mouse bite locations, and oriented to reduce bending stress	
* [ ] 6.16  Clearance around mounting holes for screws	 
* [ ] 6.17  Clearance provided around solder-in test points for probe tips
## 7 Electrical
* [ ] 7.1 What stack-up is needed?	 
* [ ] * [ ] 7.2 Polarized components are oriented correctly	 
* [ ] * [ ] 7.3 All traces are routed?	 
* [ ] * [ ] 7.4 Are decoupling capacitors placed close to power pins of ICs?	 
* [ ] * [ ] 7.5 Are analog digital commons jointed at only one point	 
* [ ] * [ ] 7.6 Does DRC pass?	 
* [ ] * [ ] 7.7 Are isolation barriers large enough?	 
* [ ] * [ ] 7.8 Are the appropriate power nets connected?
## 8 Signal Integrity
* [ ] 8.1 Are digital signals routed over separate (digital) ground planes?	 
* [ ] 8.2 Do high-speed signals avoid gaps in ground planes?	 
* [ ] 8.3 Are stubs minimized for high speed signals?	 
* [ ] 8.4 Are differential pair spacing based upon impedance matching?	 
* [ ] 8.5 Are transmission lines terminated with an appropriate impedance?	 
* [ ] 8.6 Are crystals connections short?	 
* [ ] 8.7 Is there a guard ring around the crystal?	 
* [ ] 8.8 Are there filters on A/D pins?	 
* [ ] 8.9 EMI/RFI close to entry/exit of shielded areas?	 
* [ ] 8.10 Are traces avoided under sensitive components?	 
* [ ] 8.11 Are vias avoided under metal-film resistors?	 
* [ ] 8.12 Is via fencing of sensitive RF transmission lines down with the proper via spacing? (< 1/20 lambda)	
* [ ] 8.13 Is there an option for a shielding can over sensitive circuitry e.g. RF?	 
* [ ] 8.14 Are bypass capacitors close to power pins?	 
* [ ] 8.15 Is low inductance mounting used for decoupling?
## 9 Copper Pours
* [ ] 9.1 Ground / power pins are connected and checked?	 
* [ ] 9.2 No pour between adjacent pins on ICs?	 
* [ ] 9.3 Has all layers been checked?	 
* [ ] 9.4 Are there thermal reliefs at appropriate places?	 
* [ ] 9.5 Do they introduce ground loops?
## 10 Traces
* [ ] 10.1 Are trace-pad connections sufficiently	 
* [ ] 10.2 Are the trace widths sufficient for the current draw and max heating?	 
* [ ] 10.3 No connections between adjacent pins on ICs?	 
* [ ] 10.4 Are vias for internal power traces big enough?	 
* [ ] 10.5 Is there enough space for heatsinks?	 
* [ ] 10.6 Has mitered bends or soft curves (r > 3 trace width) been implemented for impedance sensitive traces?	 
### 10.7  Sufficient width for planes/traces for required current
- * [ ] 10.7.1 Choose appropriate transmission line style (microstrip, differential pair, suspended stripline, offset stripline, coplanar wave guide)	
- * [ ] 10.7.2 Impedance match trace using dielectric constant and stack up properties	
- * [ ] 10.7.3 Use mitered or curved traces to control impedance	
## 11 Thermal
* [ ] 11.1 Are temperature sensitive components placed away from hot components?	
* [ ] 11.2 Are there thermal vias in thermal pads?	
## 12 Testing
* [ ] 12.1 Are there ground connection points close to analog test points?	
* [ ] 12.2 Are there test points for nets which are difficult to probe due to layout?	
## 13 Silk Screen
### 13.1 Notes and documentation
- * [ ] 13.1.1 Is there a revision number?	
- * [ ] 13.1.2 Is there a date?	
- * [ ] 13.1.3 Is there a blank space for a serial/assembly number?	
- * [ ] 13.1.4 Are connector pin-outs labeled?	
- * [ ] 13.1.5 Fuse size and type parked on PCB	
- * [ ] 13.1.6 Are high-density chips marked?	
#### 13.1.7 Is Functionality labeled?
- * [ ] 13.1.7.1 Test points	
- * [ ] 13.1.7.2 LEDs	
- * [ ] 13.1.7.3 Buttons	
- * [ ] 13.1.7.4 Connectors/terminals	
- * [ ] 13.1.7.5 Mounting holes	
- * [ ] 13.1.7.6 Jumpers	
### 13.2 Drafting
- * [ ] 13.2.1 No silk screen on pads	
- * [ ] 13.2.2 All text is readable from at most two directions	
- * [ ] 13.2.3 Will the silk screen be legible?	
- * [ ] 13.2.4 Are components references order by PCB layout?	
- * [ ] 13.2.5 Is there a coordinate system?	
- * [ ] 13.2.6 Text size within fab limits	
- * [ ] 13.2.7 Text mirrored properly on bottom layer	
- * [ ] 13.2.8 Test points labeled if space permits	
## 14 Final
* [ ] 14.1 Does DRC pass?	
* [ ] 14.2 Are there any superfluous vias?	
* [ ] 14.3 Does Layout Versus Schematic pass?	
## 15 Header/block
* [ ] 15.1 Name of author	 
* [ ] 15.2 Name of reviewer	 
* [ ] 15.3 Lists of revisions and changes	 
* [ ] 15.4 Date	 
* [ ] 15.5 Revision	 
* [ ] 15.6 Company / organization	 
* [ ] 15.7 Sheet / drawing number
