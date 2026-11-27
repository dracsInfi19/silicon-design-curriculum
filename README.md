# silicon-design-curriculum

Structured 12-phase learning plan covering the VLSI flow from digital design to analog and mixed-signal, ending in specialisation and placement preparation. Each phase lists topics, references, tools and a completion criterion. Progress is tracked in [docs/progress-log.md](docs/progress-log.md).

## Status

Last updated: 2026-11-25.

| Phase | Area | Status |
|---|---|---|
| 1 | Digital electronics | In progress |
| 2 | CMOS fundamentals | Not started |
| 3 | Linux and scripting basics (Linux shell, Python, git) | In progress (git remaining) |
| 4 | Verilog RTL design and basic testbenches | In progress (via [riscv-core](https://github.com/dracsInfi19/riscv-core)) |
| 5 | Computer architecture | In progress (via [riscv-core](https://github.com/dracsInfi19/riscv-core)) |
| 6 | Bus protocols and common IPs | Not started |
| 7 | SystemVerilog and verification | Not started |
| 8 | Static timing analysis | Not started |
| 9 | Synthesis, physical design and Tcl | Not started |
| 10 | Low power and DFT | Not started |
| 11 | Analog and mixed-signal basics | Not started |
| 12 | Specialisation and placement preparation | Not started |

Phases 1 to 7 form the core and are the most frequently assessed areas in VLSI campus interviews. Phases 8 to 11 provide working knowledge of the remaining areas before specialisation in Phase 12.

## Phase details

### Phase 1: Digital electronics

**Topics**
- Number systems, Boolean algebra, K-maps
- Combinational blocks: multiplexer, decoder, encoder, adders, comparators
- Latches, flip-flops, counters, shift registers
- FSMs (Mealy and Moore), state minimisation
- Setup and hold time, metastability, clock domain crossing basics

**References**
- *Digital Design*, M. Morris Mano
- *Digital Design and Computer Architecture*, Harris and Harris
- NPTEL digital circuits courses
- HDLBits (practice problems)

**Completion criterion:** design any FSM or counter on paper and explain setup and hold timing without notes.

### Phase 2: CMOS fundamentals

**Topics**
- MOSFET operation and I-V characteristics
- CMOS inverter: voltage transfer characteristic, noise margin, switching threshold
- Propagation delay, rise and fall time, logical effort
- Static and dynamic power
- CMOS gate design (NAND, NOR, complex gates), pass transistors, transmission gates
- Stick diagrams and layout basics
- Scaling and short-channel effects

**References**
- *CMOS VLSI Design*, Weste and Harris
- *Digital Integrated Circuits*, Rabaey
- *CMOS Digital Integrated Circuits*, Kang and Leblebici
- NPTEL CMOS digital VLSI design courses
- ngspice

**Completion criterion:** derive inverter delay and power by hand and simulate a NAND gate in SPICE.

### Phase 3: Linux and scripting basics

**Topics**
- Linux shell: navigation, permissions, pipes, grep, sed, awk, shell scripts
- Python basics, file I/O, regular expressions
- git: commit, branch, merge, push, pull requests

**References**
- *The Linux Command Line*, William Shotts
- Linux Journey
- MIT *The Missing Semester of Your CS Education*
- *Python for Everybody*
- *Pro Git*

**Tools:** WSL/Ubuntu, bash, git

**Completion criterion:** automate a simulation run with a shell script, parse its output with Python, and commit the result to a repository with git.

### Phase 4: Verilog RTL design and basic testbenches

**Topics**
- Synthesizable and non-synthesizable constructs
- Blocking and non-blocking assignments
- Combinational, sequential and FSM coding styles
- Parameters and generate blocks
- Self-checking testbenches and waveform debugging
- IP blocks: ALU, memory, small datapaths

**References**
- HDLBits
- *Verilog HDL*, Samir Palnitkar
- Clifford Cummings papers (sunburst-design.com)
- ChipVerify and ASIC-World tutorials

**Tools:** Icarus Verilog, GTKWave, Yosys

**Completion criterion:** write a synthesizable datapath block from scratch and verify it with a self-checking testbench.

### Phase 5: Computer architecture

**Topics**
- RV32I instruction set
- Single-cycle, multi-cycle and 5-stage pipelined datapath
- Data, control and structural hazards, forwarding, stalls
- Branch prediction, caches, memory hierarchy
- Out-of-order execution (overview)

**References**
- *Computer Organization and Design: RISC-V Edition*, Patterson and Hennessy
- Harris and Harris (RISC-V edition)
- RISC-V unprivileged ISA specification
- Onur Mutlu computer architecture lectures (ETH Zurich)
- NPTEL computer architecture courses

**Completion criterion:** the RISC-V core runs a test program and every handled hazard can be explained.

### Phase 6: Bus protocols and common IPs

**Topics**
- UART, SPI, I2C
- AMBA APB, AHB, AXI: channels, handshake, bursts
- Synchronous and asynchronous FIFO
- Clock domain crossing: synchronizers, Gray code pointers
- Arbitration basics

**References**
- ARM AMBA specifications (APB, AHB, AXI)
- Clifford Cummings CDC and asynchronous FIFO papers
- ZipCPU articles on AXI and CDC
- ChipVerify protocol pages

**Completion criterion:** implement an APB slave and a UART with testbenches, and explain the AXI handshake and asynchronous FIFO pointer logic.

### Phase 7: SystemVerilog and verification

**Topics**
- SystemVerilog data types, interfaces, classes, randomisation
- SVA assertions
- Functional coverage, constrained-random testing
- UVM basics: agent, driver, monitor, scoreboard
- Formal verification: assume, assert, cover; bounded and unbounded proofs

**References**
- Verification Academy
- *SystemVerilog for Verification*, Chris Spear
- ChipVerify SystemVerilog and UVM pages
- SymbiYosys documentation and ZipCPU formal tutorials

**Tools:** Verilator, cocotb, SymbiYosys

**Completion criterion:** build a constrained-random testbench with coverage and prove properties on a small design.

### Phase 8: Static timing analysis

**Topics**
- Setup and hold equations, slack, critical path
- Clock skew, jitter, uncertainty
- Multi-cycle paths, false paths, input and output delays
- On-chip variation, corners
- Violation fixes: buffering, sizing, retiming, pipelining

**References**
- *Static Timing Analysis for Nanometer Designs*, Bhasker and Chadha
- OpenSTA documentation

**Completion criterion:** read an OpenSTA report, locate the critical path and fix a violation by hand.

### Phase 9: Synthesis, physical design and Tcl

**Topics**
- Logic synthesis, SDC constraints, technology mapping
- Floorplanning, power planning, placement, clock tree synthesis, routing
- DRC, LVS, antenna rules
- Congestion, IR drop, signoff concepts
- Tcl syntax, procedures, lists, regular expressions
- Python and Makefile automation of tool runs and report parsing

**References**
- OpenLane and OpenROAD documentation
- Sky130 PDK documentation
- Zero to ASIC course material (Matt Venn)
- *VLSI Physical Design: From Graph Partitioning to Timing Closure*, Kahng et al.
- Official Tcl tutorials, *Practical Programming in Tcl and Tk*

**Tools:** Yosys, OpenLane, KLayout, Magic

**Completion criterion:** take an own Verilog design to GDS, explain every report, and run the full flow with a single command.

### Phase 10: Low power and DFT

**Topics**
- Power components, clock gating, power gating, multi-Vt, DVFS
- Scan design, ATPG, BIST, JTAG, fault models

**References**
- *Low-Power CMOS VLSI Circuit Design*, Kaushik Roy
- *VLSI Test Principles and Architectures*, Wang, Wu, Wen
- *Essentials of Electronic Testing*, Bushnell and Agrawal
- NPTEL VLSI testing courses

**Completion criterion:** explain scan chain operation and where clock gating reduces power.

### Phase 11: Analog and mixed-signal basics

**Topics**
- Small-signal model, common-source amplifier, current mirrors, differential pair
- Op-amp basics, feedback, stability
- PLL and ADC/DAC fundamentals

**References**
- *Fundamentals of Microelectronics*, Behzad Razavi
- *Design of Analog CMOS Integrated Circuits*, Behzad Razavi
- NPTEL analog IC design courses

**Completion criterion:** analyse an amplifier stage and explain PLL and SAR ADC operation.

### Phase 12: Specialisation and placement preparation

**Tracks**
- Primary: Design Verification (DV)
- Secondary: Physical Design (PD) and Static Timing Analysis (STA)
- Additional: RTL Design and FPGA prototyping

**Activities**
- Depth study in the primary track
- Interview question practice per topic
- Aptitude and core CS practice
- Resume and GitHub portfolio review

**Completion criterion:** answer technical interview questions across Phases 1 to 7 and demonstrate primary-track projects with documented results.

## Parallel track

- Interview preparation: 15 to 20 questions per phase, answered aloud
- Aptitude and core CS basics: short daily practice
- Project documentation: related repositories kept updated, starting with [riscv-core](https://github.com/dracsInfi19/riscv-core)
