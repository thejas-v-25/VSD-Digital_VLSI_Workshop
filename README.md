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
#**DAY 2 :**
**"Floorplanning & Placement Techniques in ASIC Design"**
## Utilization Factor (U.F.)

The **Utilization Factor** (U.F.) measures the efficiency of space usage within the core of the chip. It is the ratio of the area occupied by the **netlist** (logical design elements like gates, flip-flops, etc.) to the area of the **core** (the allocated functional area on the chip). A higher utilization factor indicates that the available core area is being used more efficiently.

### Formula:
Utilization Factor (U.F)= 
Area of Core/
Area of Netlist
​
- A higher utilization factor indicates efficient use of the chip's space.
- A lower utilization factor suggests that there is unused area in the core.

---

## Aspect Ratio

The **Aspect Ratio** refers to the ratio of the height(length) to the width of the die. It provides insight into the shape of the chip die and can affect the placement and routing of components.

### Formula:
**Aspect Ratio = Height of core / Width of core**

- An aspect ratio close to 1 (square-shaped) is preferred for better routing and efficient use of space.
- A higher or lower aspect ratio may lead to challenges in the layout design.

---

## Floorplanning and Placement

In the context of ASIC design, **Floorplanning** and **Placement** are essential stages of chip design.

- **Floorplanning** defines the high-level layout of functional blocks on the chip.
- **Placement** determines the exact locations of individual cells within the die, optimizing space and signal routing.

These steps ensure that the chip meets performance, power, and area constraints while minimizing signal delays and power consumption.

---
## Pre-Placed Cells in VLSI Design  

Pre-placed cells are critical standard cells or macros positioned early in the physical design flow before general placement.  

### Key Types of Pre-Placed Cells  
- **Clock Tree Cells**: Ensure balanced clock distribution and reduce skew.  
- **Power Management Cells**: Include decoupling capacitors (de-cap cells) to stabilize power supply and reduce noise.  
- **Logical Blockages**: Reserve space to prevent routing congestion and optimize power delivery.  

### Benefits  
- Improved **power integrity**  
- Reduced **supply noise**  
- Optimized **clock performance**  
- Efficient **routing management**
- ---
### Command to Run Floorplan in OpenLane  

To view the floorplan and placement using **Magic**, follow these steps:  

```
# Change directory to floorplan results
cd results/floorplan  

# Open the design in Magic using the SKY130A PDK
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech \
      lef read ../../tmp/merged.lef \
      def read picorv32a.placement.def &
```

![4](https://github.com/user-attachments/assets/b24eb6a7-10d7-4236-b55b-87bd8c95819f)
![4a](https://github.com/user-attachments/assets/9fb4e906-ac64-4c8e-a870-bee85474a324)

---
![5](https://github.com/user-attachments/assets/a304f1cf-f33b-481e-9b7a-63e21fd4c443)

---

![7](https://github.com/user-attachments/assets/59a2cdf9-ff2e-4a5e-a3d1-a28af263f0d2)

![8](https://github.com/user-attachments/assets/a7d98a60-1018-4389-bcb3-6a244cfc2db8)

![9](https://github.com/user-attachments/assets/8a1ba59c-6466-4cf6-9785-d451e9297c20)

For navigating in magic layout use the mouse and press V for fitting the window ,
Z - for zoom ,
S - for selecting

![10](https://github.com/user-attachments/assets/7f730b34-4e13-4edf-a935-773b5b405729)


![11](https://github.com/user-attachments/assets/8abd8937-a57b-4123-b6a0-ca3cbb17057f)

#Preview of the placement in the magic tool in openlane

![12](https://github.com/user-attachments/assets/5c7edb15-c117-4e74-91fc-ae124f2663ac)
Cell Design and Characterization
Cell Design:
In VLSI, a cell is a fundamental building block used to construct digital circuits.
Cells include basic logic gates (AND, OR, NOT), flip-flops, latches, and more.
Design Flow:
Schematic Design: Create a transistor-level circuit for the desired logic.
Layout Design: Generate a physical layout (arrangement of transistors, metal layers, and vias) while minimizing area and adhering to design rules.
Verification: Ensure the layout matches the schematic (LVS - Layout vs. Schematic) and meets manufacturing rules (DRC - Design Rule Check).
Characterization:
Characterization involves analyzing and modeling the electrical behavior of cells under various conditions.
Key steps include:
Delay Calculation: Measure propagation delay for different input transitions and loads.
Power Analysis: Evaluate dynamic and static power consumption.
Timing Characterization: Generate timing parameters like setup/hold times and clock-to-output delays.
Library Generation: Create standard cell libraries (e.g., Liberty files) for use in digital design tools.

##**DAY -3**


