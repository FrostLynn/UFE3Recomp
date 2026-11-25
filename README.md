# UFE3Recomp

A static recompilation project for **Ultraman Fighting Evolution 3** (PlayStation 2), aiming to lift the game's original Emotion Engine (MIPS R5900) binary into portable C/C++ paired with native hardware and OS shims.

> **Disclaimer:** This repository does not include any copyrighted game files, BIOS dumps, or assets. You must provide your own legally obtained copy of *Ultraman Fighting Evolution 3* (ISO or extracted disc files) to extract and recompile the game.

## Status

Early setup — workspace initialized, awaiting target game binary inspection and lifter/runtime scaffolding.

## Goals

- Lift the PS2 Emotion Engine executable to portable C/C++.
- Implement lightweight HLE (High-Level Emulation) shims for EE kernel syscalls, IOP peripherals (controller, memory card, CDVD, SPU2), and Graphics Synthesizer / VU rendering.
- Build and run natively without full-system CPU emulation.
