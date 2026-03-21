# 5-Stage-RISC-Pipelined-Processor
This is a 32-bit 5-stage pipelined processor I built from scratch in Verilog. It covers the full standard architecture: Instruction Fetch (IF), Decode (ID), Execute (EX), Memory Access (MEM) and Write-Back (WB). The core uses a non-overlapping two-phase clocking system (clk1/clk2) to manage timing across the stages and keep the register bank stable
