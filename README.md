# Performance Comparison of CMOS and TGL-Based Low-Power Full Adders  

---

##  Project Overview

This project presents the design, analysis, and performance comparison of two 1-bit full adders implemented using:

- **Conventional CMOS logic**, and  
- **Transmission Gate Logic (TGL)**  

Both designs are evaluated at **multiple levels of the VLSI design flow**, including:

- RTL / behavioral verification in **ModelSim**
- Transistor-level schematic design and simulation in **Cadence Virtuoso**
- Synthesis, timing, power, and area analysis in **Synopsys Design Compiler**
- Full custom layout in **Cadence Virtuoso Layout Suite**
- Waveform, power, and propagation delay analysis

This end-to-end flow demonstrates the strengths and limitations of CMOS vs. TGL logic in low-power arithmetic circuits.

---

##  Objective

The primary objective is to **design and evaluate** a 1-bit full adder using two logic styles:

- Standard CMOS logic  
- Transmission Gate Logic (TGL)

and compare them based on:

- **Power consumption**  
- **Propagation delay**  
- **Silicon area / transistor count**  
- **Overall efficiency for VLSI applications**

The project aims to determine which logic style is better suited for **low-power, high-performance** digital systems such as mobile devices, IoT nodes, and embedded processors.

---

##  Background Summary

Traditional CMOS full adders are robust and widely used, but:

- Consume more dynamic and static power  
- Use more transistors  
- Occupy larger area  

Transmission Gate Logic (TGL):

- Uses complementary NMOS + PMOS pairs  
- Provides full swing signals  
- Reduces leakage and switching activity  
- Achieves lower power and better speed  
- Uses fewer transistors  

Thus, TGL is a promising alternative for next-generation low-power adders.

---

##  Tools & Technologies Used

| Task | Tools |
|------|-------|
| RTL modeling & functional simulation | ModelSim |
| Transistor-level schematic & transient analysis | Cadence Virtuoso |
| Power & timing simulation | Cadence ADE L / ADE XL |
| Synthesis (gate-level) | Synopsys Design Compiler |
| Layout design | Cadence Virtuoso Layout XL |
| PDK used | GPDK045 (45 nm technology) |

---

##  Methodology

### **1️ Functional Verification (ModelSim)**  
- Verilog behavioral models for CMOS and TGL full adders  
- Testbench applying all 8 input combinations  
- Verified correctness of Sum and Cout outputs  
- Confirmed truth table-based behavior  

### **2️ Schematic Design (Cadence Virtuoso)**  
- Transistor-level CMOS and TGL designs created in GPDK045  
- VPulse sources applied for realistic switching  
- Symbol generation for hierarchical simulation  
- Testbench schematic created for transient testing  

### **3️ Transient Analysis (Cadence ADE L)**  
- Simulated propagation delay  
- Simulated average dynamic power  
- Extracted waveforms and measured delay using Calculator functions  

### **4️ Synthesis & Performance Analysis (Synopsys DC)**  
- Synthesized Verilog RTL into gate-level netlists  
- Generated power, area, and timing reports  
- Compared gate count and critical path timings  

### **5️ Layout Design (Virtuoso Layout XL)**  
- Generated layouts for CMOS and TGL full adders  
- Ensured proper DRC and LVS checks  
- Routed signals across Metal1/Metal2 layers  
- Created final clean layout ready for GDS export  

---

## Results Summary

### **CMOS Full Adder**
| Metric | Value |
|--------|-------|
| Average Power (Virtuoso) | **16.87 µW** |
| Propagation Delay | **10.14 ns** |
| Synthesized Area | **5.054 µm²** |
| Total Synthesized Power | **4.7582 µW** |

---

### **TGL Full Adder**
| Metric | Value |
|--------|-------|
| Average Power (Virtuoso) | **3.274 µW** |
| Propagation Delay | **9.923 ns** |
| Synthesized Area | **5.054 µm²** |
| Total Synthesized Power | **4.7582 µW** |

---

## Final Comparison

| Feature | CMOS | TGL | Winner |
|--------|------|-----|--------|
| Average Power | 16.87 µW | **3.27 µW** |  TGL |
| Delay | 10.14 ns | **9.923 ns** |  TGL |
| Synthesized Area | 5.054 µm² | 5.054 µm² |  Tie |
| Signal Integrity | High | **Very High (Full Swing)** |  TGL |
| Transistor Count | High | **Lower** |  TGL |

** TGL is significantly more power-efficient and slightly faster while maintaining identical area.**

---

##  Repository Structure

