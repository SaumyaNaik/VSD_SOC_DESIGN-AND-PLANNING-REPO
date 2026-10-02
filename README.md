# VSD_SOC_DESIGN-AND-PLANNING-REPO
VSD SoC Design and Planning program, covering Open-source EDA tools, OpenLANE, SKY130 PDK, RTL-to-GDSII flow, and SoC design concepts
# Day-01: Inception of open-source EDA, OpenLANE and Sky130 PDK
<img width="1920" height="1080" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/3b7118e5-af36-432d-8422-f08087f5b2ac" />
System-on-Chip(SoC) Basics: 

A System-on-Chip integrates multiple functional blocks onto one chip. Typical blocks include a processor, memories, peripherals, interfaces and technology-specific IP.

<img width="1920" height="1080" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/1d286bb7-6e0a-41c6-af54-a97a2f9ca309" />

<img width="1920" height="1080" alt="Screenshot (74)" src="https://github.com/user-attachments/assets/b1cd64ab-4089-4882-8219-5fabd3a0ac26" />

* Introduction to QFN-48 Package:

  - QFN-48 (Quad Flat No-Lead 48) is a semiconductor IC package that has 48 electrical connections (pads) around the bottom edges of the package. Unlike traditional packages, QFN has no external leads/pins, making it compact and suitable for modern SoC and VLSI designs.

Important Terms:

  - Package: The outer physical structure that protects the semiconductor die and provides electrical connections between the chip and the PCB.

  - QFN-48: A package with 48 pads, arranged around four sides, plus a central exposed pad in many QFN designs for thermal and/or electrical purposes.

<img width="1920" height="1080" alt="Screenshot (75)" src="https://github.com/user-attachments/assets/7738bf3b-8038-4bd3-be34-85cb18fe848e" />

Components of chip:

* Pad: A metal contact area used to connect the IC to the outside world, typically through PCB soldering. Pads can carry power, ground, input/output signals, etc.

* Die: The actual piece of semiconductor material (usually silicon) containing the fabricated electronic circuits, such as CPU, memory, and other SoC blocks.

* Core: The main functional region of the die where the logic circuitry is placed. In physical design, the core area generally contains standard cells and other internal circuit elements, while the surrounding area contains I/O-related structures.

<img width="1920" height="1080" alt="Screenshot (76)" src="https://github.com/user-attachments/assets/d1518a45-9c6a-4ae5-bb2e-48262c7ca4c4" />

1.Foundry:

A foundry is a semiconductor manufacturing company that fabricates ICs/SoCs on silicon wafers based on a chip design provided by a designer.

Converts the RTL/physical design into a physical silicon chip.

Provides the required Process Design Kit (PDK).

Defines technology rules such as technology node, design rules, metal layers, and standard cell libraries.

Examples: TSMC, Samsung Foundry, Intel Foundry.

2.Macros:

Macros are relatively large, pre-designed blocks used inside an SoC.

Examples:

SRAM / ROM

PLL

ADC/DAC

USB controller

Memory controllers

Macros are generally treated as fixed or pre-designed blocks during physical design rather than being built from individual standard cells.

3.Foundry IPs:

Foundry IPs are pre-designed and verified intellectual-property blocks provided by the foundry or its ecosystem, designed to work with a particular semiconductor process.

Examples:

Standard-cell libraries

I/O libraries

SRAM memories

PLLs

ESD protection cells

Analog/mixed-signal IPs

They help designers avoid designing every low-level circuit from scratch and ensure compatibility with the chosen fabrication technology.

# Introduction to RISC-V 


<img width="1920" height="1080" alt="Screenshot (78)" src="https://github.com/user-attachments/assets/09d218f8-846d-4e44-8bd2-95fd4a6595a0" />

An Instruction Set Architecture is an abstract interface between software and processor hardware. It defines the instructions, registers, memory-access behavior and programmer-visible rules of the processor.
The ISA allows software to be developed against a defined instruction interface while different hardware implementations can realize that same ISA.

* RISC-V

RISC-V is an open standard ISA based on reduced-instruction-set principles. It can be implemented in many different processor designs and is widely used for education, research and hardware development.

*PicoRV32

PicoRV32 is a compact RISC-V CPU core. In this learning flow, the conceptual path is RISC-V ISA → CPU implementation → RTL → synthesis → physical design.


# From Software Application to Hardware  

<img width="1920" height="1080" alt="Screenshot (79)" src="https://github.com/user-attachments/assets/e42fa3f5-0e57-4b33-bb35-e09a34864a24" />

<img width="1920" height="1080" alt="Screenshot (80)" src="https://github.com/user-attachments/assets/9540b881-7290-43ee-95c4-b4f7a81b02c2" />

Layer	              :                                           Role

Application software	:                          Programs used by the user, such as a browser or stopwatch application.

Operating system / system software	 :          Manages I/O, memory and other hardware resources and provides services to applications.

Compiler	:                                     Translates high-level source code such as C into lower-level instructions.

Assembler	   :                                  Converts assembly instructions into machine-code representation.

ISA	   :                                        Defines the instructions and programmer-visible interface of a processor.

RTL	   :                                        Describes digital hardware behavior and data movement using HDL such as Verilog.

Synthesis   :                                  	Converts RTL into a gate-level representation for a target technology.

Physical design	  :                             Places and routes the design and prepares the physical layout.

Part 1: RISC-V Instruction Set Architecture((ISA)
Part 2: RTL and synthesis of RISC-V based CPU core-picorv32a
Part 3: Physical Design Implementation 

# SoC Design and Openlane :Introduction to all sources of open source and digital asic design

<img width="1920" height="1080" alt="Screenshot (81)" src="https://github.com/user-attachments/assets/25c83fcd-8a63-4bb3-b764-26b6ddeb3741" />

1. EDA Tools

EDA (Electronic Design Automation) tools are software tools used to design, simulate, synthesize, place, route, and verify electronic circuits such as ASICs.
In an ASIC design flow, EDA tools automate many complex design tasks.

Examples:

OpenROAD – used for physical design tasks such as placement, clock tree synthesis, routing, etc.

OpenLane – an automated RTL-to-GDSII ASIC design flow.

Qflow – an open-source digital synthesis and physical-design flow.

Role of EDA tools:

EDA tools convert the RTL design into a physical chip layout by performing steps such as:
Logic synthesis, Floorplanning, Placement, Clock Tree Synthesis, Routing, Design verification and sign-off

2. RTL Designs

RTL (Register Transfer Level) describes the digital circuit in terms of:
Registers, Combinational logic, Data transfers between registers, Clocked operations

RTL is generally written using hardware description languages such as:
Verilog, SystemVerilog, VHDL

Example:

A Verilog description of an ALU, processor, counter, or memory controller can be considered an RTL design.
The RTL is the starting point of the ASIC physical-design flow. It is given to synthesis tools, which convert it into a gate-level representation.

Examples of open-source RTL designs:
librecores.org, opencores.org, and repositories available on GitHub.

3. PDK Data

PDK (Process Design Kit) is a collection of technology-specific files and information provided for designing chips using a particular semiconductor manufacturing process. In the "age of Gods", the design of an IC was tightly integrated with the manufacturing process available within each company.
It acts as the connection between the circuit design and the fabrication process.

PDK contains information such as: Standard-cell information, Design rules, Technology files, Layer definitions, Timing information, SPICE models, Physical and electrical characteristics

Example: SkyWater 130 nm PDK

The lecture refers to the SkyWater 130 nm open-source PDK, which provides the technology information required to design and fabricate circuits using the 130 nm process.

RTL tells us what the circuit should do, while the PDK tells the EDA tools how that circuit can be physically implemented in a particular technology.

<img width="1920" height="1080" alt="Screenshot (82)" src="https://github.com/user-attachments/assets/3fb8c04b-e4ed-416d-836b-0367428ce3ed" />

Is 130 nm Fast?

Yes, 130 nm technology can achieve relatively high operating frequencies, depending on the circuit architecture, standard cells, design constraints, and physical implementation.

The lecture gives examples showing that 130 nm is capable of high-speed digital operation:

An OSU team reported approximately 327 MHz post-layout frequency for a single-cycle RV32I CPU using the SkyWater 130 nm technology.

A pipelined version can achieve more than 1 GHz according to the lecture.

It also compares this with the historical Intel Pentium 4 Extreme Edition, which operated at 3.46 GHz.


# Simplied RTL to GDSII Flow:

<img width="1920" height="1080" alt="Screenshot (83)" src="https://github.com/user-attachments/assets/21b16bc3-0992-4be3-9256-09d6f96fd4c1" />

RTL to GDSII is also called Automated PnR and/or Physical Implementation 

* Synthesis: Synthesis converts the RTL description into a gate-level netlist using standard cells from the target technology.
It maps operations described in RTL to physical logic gates such as:
AND, OR, NOT, Flip-flops, Multiplexers

RTL:It converts RTL to a crcuit out of components from the standard cell library(scl)
- "Standard Cells" have regular layout
- Each has different views/models like
  - Electrical, HDL,SPICE - layout(bstrct & Detailed)

* Floor and Power Planning: 
  - Chip Floor Planning : Partition the chip die between different system building blocks and place the I/O pads
    - It decides: Chip/core dimensions,, Placement regions, Locations of major blocks, I/O locations
  - Power Floor Planning : Power pads are connected to between components Power straps and rings.
    - Creates the power-distribution network to deliver: VDD, VSS/GND to different parts of the chip.

* Placement : The synthesized standard cells are physically placed inside the chip's core area.
   - Usual done in 2 steps Global and Detailed

* Clock-Tree Synthesis : Clock Tree Synthesis creates a clock distribution network connecting the clock source to all sequential elements such as flip-flops.
   - The main objective is to minimize clock skew and ensure that the clock reaches different registers with appropriate timing.

* Routing : Routing connects all the placed cells according to the netlist. Implement the interconnect using the available metal layer 

   - There are generally two stages:
     - Global routing – determines approximate routing paths.
     - Detailed routing – creates the actual metal-layer connections.
  
Routing is huge.The result is a physically connected design.

* Sign-off : Sign-off is the final verification stage before generating the final layout.
   - Physical Verification
      - Design Rule Checking (DRC)
      - Layout vs. Schematic (LVS)
   - Timing Verification
      - State Timing Analysis (STA)
GDSII

After successful sign-off, the final physical layout is exported as a GDSII file.

GDSII (Graphic Design System II) is a standard file format used to represent the physical layout of an integrated circuit.

# Introduction to Openlane 

Started as an Open-source Flow for a True Open Source Tape-out Experiment

OpenLANE ASIC Flow

 <img width="1920" height="1080" alt="Screenshot (85)" src="https://github.com/user-attachments/assets/159307d7-0264-473b-873f-a96d5350fecd" />

Main Goal : Produce a clean GDSII with no human intervention(no-human-in-the-loop)

* Clean means : No LVS Violation , No DRC Violation, Timing Violation
  Can be used to harder Macros and Chips
   
Two modes of operations : Autonomous or Interactive 

Design Space Explaination 

Large number of design experiment

