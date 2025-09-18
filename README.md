<details>
	<summary>Day 0 - Getting started with VLSI SOC DESIGN and PLANNING </summary>

# Day 0 - Getting started with VLSI SOC DESIGN and PLANNING

An SoC is a single chip that integrates multiple components of a complete electronic system (CPU, memory, I/O, communication blocks, etc.).
Instead of having separate chips for processor, memory, and peripherals → everything is put on one silicon die.
In VLSI (Very-Large-Scale Integration), SoC design is one of the most advanced applications — because it combines digital, analog, memory, RF, and sometimes sensors into one chip.

<img width="1712" height="217" alt="Screenshot 2025-09-18 233255" src="https://github.com/user-attachments/assets/8e22b9a8-0b96-4523-a3da-cb645ba6ed2c" />

The Specification and High-Level Model (C Model)
O1 —— Specs (C model): This is the starting point.

Specs: These are the detailed requirements for the chip. They define what the chip must do (its function, performance, power consumption, etc.), but not how it will be implemented in hardware.

C model: To validate the specifications, engineers first create a software model of the chip's functionality written in the C programming language. This is a high-level, behavioral model that is fast to simulate and easy to modify. It acts as the "golden reference" — a perfect software representation of what the chip should do.

Using RTL (Verilog): The architect implements the design using a Hardware Description Language (HDL), specifically Verilog, at the Register-Transfer Level (RTL)

Testbench is in C language: This is the most crucial part of the diagram for verification. A testbench is a setup that applies stimuli (test inputs) to a design and checks its outputs against expected results.

The same C testbench that was used to verify the C model (O1) is now used to verify the RTL model (O2).

Soft copy of the Hardware: This refers to the final, verified RTL code (the Verilog files). This is called a "soft copy" because it is the digital design files that fully describe the hardware. This RTL code is then sent through subsequent automated steps in the chip design flow (like Synthesis and Place & Route) to be turned into a physical "hard" chip.

<img width="1012" height="413" alt="Screenshot 2025-09-18 233313" src="https://github.com/user-attachments/assets/9aae355a-bde0-4fe4-b2d1-83efbe6cb606" />


This diagram illustrates the physical implementation phase of chip design. It starts with the verified RTL code (the "soft copy" from the previous diagram) and shows the key components and steps involved in converting that abstract description into a detailed, technology-specific circuit model (a netlist).

The diagram shows that the RTL code is organized into the main components of the System-on-a-Chip (SoC):

Processor: The central processing unit (CPU) core(s).

Peripherals/IPs: The surrounding functional blocks, such as memory controllers, USB interfaces, graphics processors (GPUs), etc.

**The Outputs: The Results of Synthesis -->**
This is the core of the image. The term "Synthesis" is the process of using automated Electronic Design Automation (EDA) tools to translate the high-level RTL code into a list of specific logic gates and their interconnections (a netlist), based on a chosen semiconductor technology library (e.g., a 3nm Samsung process).

**Gate Level Netlist (synth P&R)**

What it is: A detailed netlist for the digital logic that was described in the main RTL. It consists of standard cells (basic logic gates like AND, OR, flip-flops) from the technology library.

(synth P&R) means this netlist is the input for the next major stage: Place and Route (P&R), where the gates are physically arranged on the silicon die and the wires connecting them are drawn.

**Macros (synth RTL)**

What it is: "Macros" typically refer to large, pre-designed blocks with a fixed layout, such as Memory (SRAM, DRAM) or Processor Cores.

(synth RTL) indicates that these macros are synthesized from their own RTL descriptions separately. They are not broken down into standard cells like the main logic. They are generated or imported as complete, black-box units with a fixed physical interface and layout.

**Analog IPs (func RTL)**

What it is: These are blocks that interface with the real, continuous world, such as Phase-Locked Loops (PLLs), Analog-to-Digital Converters (ADCs), or USB PHYs.

(func RTL) is crucial. It means that for the digital part of the chip to be simulated and verified, these analog blocks are represented by a Functional RTL model. T



