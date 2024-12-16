# VSD-Digital_VLSI_Workshop
**VSD - Digital VLSI SoC Design and Planning**  
Digital VLSI SoC Workshop  

---

## **Overview**
This repository contains materials, resources, and examples from the Digital VLSI System-on-Chip (SoC) Workshop. The workshop focuses on introducing participants to the design, simulation, and implementation of digital VLSI circuits and SoC concepts.

---

## **Day 1: Introduction to RISC-V ISA and OpenLane ASIC Design Flow**

### **RISC-V ISA Overview**
- **RISC-V** is a free and open Instruction Set Architecture (ISA) designed for flexibility and modularity.
- It supports various extensions like:
  - Integer Arithmetic (`I`)
  - Multiplication (`M`)
  - Atomic Operations (`A`)
  - Floating-Point (`F`, `D`)

#### **Key Features**
- Open-source, royalty-free.
- Simplified design for power efficiency and scalability.
- Applications:
  - Microcontrollers
  - IoT Devices
  - AI Accelerators, and more.

---

### **OpenLane ASIC Design Flow**
- **OpenLane** is an open-source toolchain for ASIC design, leveraging tools like Yosys, Magic, and OpenROAD.
- It provides a complete **RTL-to-GDSII flow**.

#### **Key Steps in the Flow**
1. **RTL Design**: Writing the digital logic (e.g., Verilog code).
2. **Synthesis**: Converting RTL to a gate-level netlist.
3. **Floorplanning**: Allocating space for the design components.
4. **Placement & Routing**: Placing cells and connecting them.
5. **GDSII Generation**: Final layout for fabrication.

---

## **Invoking OpenLane in the Terminal**

To invoke **OpenLane**, use the following steps in your terminal:

```bash
# Navigate to the working directory
cd ~/Desktop
cd work/tools/

# Verify the contents
ls -ltr

# Enter the OpenLane working directory
cd openlane_working_dir

# Confirm the current path
pwd

# Start OpenLane in interactive mode
docker
./flow.tcl -interactive

# Load OpenLane package
package require openlane
