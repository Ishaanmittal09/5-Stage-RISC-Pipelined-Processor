# 5-Stage-RISC-Pipelined-Processor

This is a **32-bit MIPS-inspired 5-stage pipelined processor** I built from scratch in Verilog. It implements the full standard architecture: Instruction Fetch (**IF**), Decode (**ID**), Execute (**EX**), Memory Access (**MEM**), and Write-Back (**WB**).

### ⚡ Technical Highlights
* **Two-Phase Clocking:** The core utilizes a **non-overlapping two-phase clocking system** (`clk1`/`clk2`). This was a deliberate design choice to manage timing across the pipeline stages and ensure the register bank remains stable without race conditions.
* **Hazard Management:** Currently, data hazards are handled via **Software Stalling** (manual NOPs/dummy instructions). This allows the pipeline to remain stable while successfully verifying the correctness of the data path and control logic.
* **Factorial Verification:** The processor’s reliability was verified by calculating **7! (Factorial of 7)**. The loop logic, branch offsets, and accumulator successfully returned **5040** in the Vivado Tcl console.

### 📜 Instruction Set Architecture (ISA)
* **Arithmetic/Logic:** `ADD`, `SUB`, `MUL`, `AND`, `OR`, `SLT`
* **Immediate Operations:** `ADDI`, `SUBI`, `SLTI`
* **Data Transfer:** `LW` (Load Word), `SW` (Store Word)
* **Control Flow:** `BEQZ`, `BNEQZ`, `HLT`

### 🛠 Tools & Simulation
* **Language:** Verilog (RTL)
* **Simulator:** AMD Vivado 2024.2
* **Verification:** Three distinct testbenches covering ALU ops, Memory R/W, and Branching Loops.

### 🚀 How to Run
1. Open the project in **Vivado**.
2. Add `RISC.v` as the design source.
3. Add the testbench files (`RISC_tb1.v`, `RISC_tb2.v`) to **Simulation Sources**.
4. Right-click the desired testbench (`RISC_tb1` or `RISC_tb2`) and select **Set as Top**.
5. Run **Behavioral Simulation** and observe the register updates in the Tcl Console.
