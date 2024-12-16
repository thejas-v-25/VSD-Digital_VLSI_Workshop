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
![1_a](https://github.com/user-attachments/assets/22dca635-c66e-4d31-8717-d8981c07bc2c)

```
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
```
![2_a](https://github.com/user-attachments/assets/e0d5e347-d98a-4a0c-bb3d-4c811b47f5dc)
![1](https://github.com/user-attachments/assets/949e2ead-d423-4515-a461-cc200fb0e983)

### **Calculating Flop Ratio**

The **Flop Ratio** is calculated using the following formula:

```math
Flop\ Ratio = \frac{Number\ of\ D\ Flip\ Flops}{Total\ Number\ of\ Cells}
```

Where:  
- **D Flip-Flops (DFF)** = 1613  
- **Total Cells** = 14876  

Thus, the **Flop Ratio** is:

```math
Flop\ Ratio = \frac{1613}{14876}
```
 = 0.1084 or 10.84% 

### **Flop Ratio Calculation Diagram**
![Flop Ratio Calculation Diagram](https://github.com/user-attachments/assets/2579b133-df62-4c7f-bf49-1a492e7226af)

---
#**DAY 2 **
**"Floorplanning & Placement Techniques in ASIC Design"**
## Utilization Factor (U.F.)

The **Utilization Factor** (U.F.) measures the efficiency of space usage within the core of the chip. It is the ratio of the area occupied by the **netlist** (logical design elements like gates, flip-flops, etc.) to the area of the **core** (the allocated functional area on the chip). A higher utilization factor indicates that the available core area is being used more efficiently.

### Formula:
Utilization Factor (U.F)= 
Area of Core/
Area of Netlist
​

