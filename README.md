# VSD-Digital_VLSI_Workshop
VSD - Digital VLSI SoC design and planning
Digital VLSI SoC Workshop

Overview

This repository contains materials, resources, and examples from the Digital VLSI System-on-Chip (SoC) Workshop. The workshop focuses on introducing participants to the design, simulation, and implementation of digital VLSI circuits and SoC concepts.
##Day 1 
Introduction to RISC-V ISA and OpenLane ASIC Design Flow
RISC-V ISA Overview:
RISC-V is a free and open Instruction Set Architecture (ISA) designed for flexibility and modularity.
It supports various extensions like integer arithmetic (I), multiplication (M), atomic operations (A), and floating-point (F, D).
Key Features:
Open-source, royalty-free.
Simplified design for power efficiency and scalability.
Applications: Microcontrollers, IoT, AI accelerators, and more.
OpenLane ASIC Design Flow:
OpenLane is an open-source toolchain for ASIC design, leveraging tools like Yosys, Magic, and OpenROAD.
It provides a complete RTL-to-GDSII flow.
Key Steps in the Flow:
RTL Design: Writing the digital logic (e.g., Verilog code).
Synthesis: Converting RTL to a gate-level netlist.
Floorplanning: Allocating space for the design components.
Placement & Routing: Placing cells and connecting them.
GDSII Generation: Final layout for fabrication.
#Invoking openalne in terminal
''' 
cd ~Desktop 
cd work/tools/
ls -ltr
cd openlane_working_dir
pwd 
docker
./flow.tcl -interactive
package require openlane 
