# VSD_SOC_DESIGN-AND-PLANNING-REPO
VSD SoC Design and Planning program, covering Open-source EDA tools, OpenLANE, SKY130 PDK, RTL-to-GDSII flow, and SoC design concepts
# Day-01: Inception of open-source EDA, OpenLANE and Sky130 PDK
<img width="1920" height="1080" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/3b7118e5-af36-432d-8422-f08087f5b2ac" />
System-on-Chip(SoC) Basics: 

A System-on-Chip integrates multiple functional blocks onto one chip. Typical blocks include a processor, memories, peripherals, interfaces and technology-specific IP.

<img width="1920" height="1080" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/1d286bb7-6e0a-41c6-af54-a97a2f9ca309" />

<img width="1920" height="1080" alt="Screenshot (74)" src="https://github.com/user-attachments/assets/b1cd64ab-4089-4882-8219-5fabd3a0ac26" />

Introduction to QFN-48 Package:

QFN-48 (Quad Flat No-Lead 48) is a semiconductor IC package that has 48 electrical connections (pads) around the bottom edges of the package. Unlike traditional packages, QFN has no external leads/pins, making it compact and suitable for modern SoC and VLSI designs.

Important Terms:

Package: The outer physical structure that protects the semiconductor die and provides electrical connections between the chip and the PCB.

QFN-48: A package with 48 pads, arranged around four sides, plus a central exposed pad in many QFN designs for thermal and/or electrical purposes.

<img width="1920" height="1080" alt="Screenshot (75)" src="https://github.com/user-attachments/assets/7738bf3b-8038-4bd3-be34-85cb18fe848e" />

Components of chip:

Pad: A metal contact area used to connect the IC to the outside world, typically through PCB soldering. Pads can carry power, ground, input/output signals, etc.

Die: The actual piece of semiconductor material (usually silicon) containing the fabricated electronic circuits, such as CPU, memory, and other SoC blocks.

Core: The main functional region of the die where the logic circuitry is placed. In physical design, the core area generally contains standard cells and other internal circuit elements, while the surrounding area contains I/O-related structures.

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

<img width="1920" height="1080" alt="Screenshot (78)" src="https://github.com/user-attachments/assets/abe7aa6f-0d1d-4374-bfa8-1c8eb262e70d" />


An Instruction Set Architecture is an abstract interface between software and processor hardware. It defines the instructions, registers, memory-access behavior and programmer-visible rules of the processor.
The ISA allows software to be developed against a defined instruction interface while different hardware implementations can realize that same ISA.

RISC-V

RISC-V is an open standard ISA based on reduced-instruction-set principles. It can be implemented in many different processor designs and is widely used for education, research and hardware development.

PicoRV32

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






