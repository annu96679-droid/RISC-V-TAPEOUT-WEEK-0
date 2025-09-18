<details>
	<summary>Day 0 - Getting started with VLSI SOC DESIGN and PLANNING </summary>

# Day 0 - Getting started with VLSI SOC DESIGN and PLANNING

An SoC is a single chip that integrates multiple components of a complete electronic system (CPU, memory, I/O, communication blocks, etc.).
Instead of having separate chips for processor, memory, and peripherals → everything is put on one silicon die.
In VLSI (Very-Large-Scale Integration), SoC design is one of the most advanced applications — because it combines digital, analog, memory, RF, and sometimes sensors into one chip.

<img width="1712" height="217" alt="Screenshot 2025-09-18 233255" src="https://github.com/user-attachments/assets/8e22b9a8-0b96-4523-a3da-cb645ba6ed2c" />

The Specification and High-Level Model (C Model)
O1 —— Specs (C model): This is the starting point.

Define Specifications: The desired features and performance of the chip are written down.

Create a C Model: A software model in C is written to emulate the chip's behavior based on the specs. This model is verified to be correct.

Develop a C Testbench: Tests are written in C to put the model through its paces, generating inputs and checking outputs.

RTL Design: An RTL architect translates the behavior of the C model into a hardware implementation described in Verilog.

Functional Verification: The same C testbench from step 3 is used to test the Verilog RTL model. The outputs of the RTL model are compared to the known-good outputs from the C model.

Iterate: If the outputs don't match, the RTL code (and potentially the C model or specs) is debugged and fixed until they do.

Completion: Once verified, the RTL code is the "soft copy" of the hardware and is ready for the next stages of physical chip design.
