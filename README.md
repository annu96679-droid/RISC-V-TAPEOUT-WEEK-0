<details>
	<summary>Day 0 - Getting started with VLSI SOC DESIGN and PLANNING </summary>

# Day 0 - Getting started with VLSI SOC DESIGN and PLANNING

An SoC is a single chip that integrates multiple components of a complete electronic system (CPU, memory, I/O, communication blocks, etc.).
Instead of having separate chips for processor, memory, and peripherals → everything is put on one silicon die.
In VLSI (Very-Large-Scale Integration), SoC design is one of the most advanced applications — because it combines digital, analog, memory, RF, and sometimes sensors into one chip.

The Specification and High-Level Model (C Model)
O1 —— Specs (C model): This is the starting point.

Specs: These are the detailed requirements for the chip. They define what the chip must do (its function, performance, power consumption, etc.), but not how it will be implemented in hardware.

C model: To validate the specifications, engineers first create a software model of the chip's functionality written in the C programming language. This is a high-level, behavioral model that is fast to simulate and easy to modify. It acts as the "golden reference" — a perfect software representation of what the chip should do.
