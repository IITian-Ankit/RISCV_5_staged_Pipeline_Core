# RISC-V 5-Stage Pipelined Processor

## 📜 Project Overview
This project implements a **5-stage pipelined RISC-V processor** in **Verilog HDL**, designed to execute RV32I instructions.  
It follows the classic RISC pipeline architecture to improve instruction throughput by overlapping different execution stages.  

The processor includes **hazard detection** and **forwarding units** to handle data and control dependencies, also ensures correct execution without stalling performance unnecessarily.

---

## 🏗 Pipeline Stages
The design consists of the following stages:

1. **Instruction Fetch (IF)**  
   - Fetches the instruction from memory using the **Program Counter (PC)**.  
   - PC update logic includes branch and jump handling.  

2. **Instruction Decode / Register Fetch (ID)**  
   - Decodes the fetched instruction.  
   - Reads operands from the register file.  
   - Generates control signals for execution and memory operations.  

3. **Execute (EX)**  
   - Performs ALU operations (arithmetic, logical, shifts, comparisons).  
   - Calculates branch target addresses.  
   - Determines branch/jump outcomes.  

4. **Memory Access (MEM)**  
   - Reads from or writes to data memory for load/store instructions.  

5. **Write Back (WB)**  
   - Writes results back into the register file.  

---

## ⚙️ Hazard Handling

### **Data Hazards**
- **Forwarding Unit**: Forwards results from EX/MEM or MEM/WB stages to EX stage inputs when needed.  
- **Stall Logic**: Inserts bubbles when forwarding is not possible (e.g., load-use hazard).

### **Control Hazards**
- **Branch Prediction**: Static branch decision (e.g., predict not taken).  
- **Flush Logic**: Flushes instructions in the pipeline on a branch/jump misprediction.

--Credits to RISC-V Transistors to AI Tutorial.

-Feel free to make suitable changes if there is a scope of improvement in the code.

--To Contact:

1.Linkedin-- www.linkedin.com/in/ankit310

2.Gmail-- ankit.ghanshyam.23042@iitgoa.ac.in
