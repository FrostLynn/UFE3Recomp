# UFE3Recomp

A static recompilation project for **Ultraman Fighting Evolution 3** (PlayStation 2), aiming to lift the game's original Emotion Engine (MIPS R5900) binary into portable C/C++ paired with native hardware and OS shims.

> **Disclaimer:** This repository does not include any copyrighted game files, BIOS dumps, or assets. You must provide your own legally obtained copy of *Ultraman Fighting Evolution 3* (ISO or extracted disc files) to extract and recompile the game.

## Status

ISO extracted into `disc/` and main binary inspected. Ready to analyze function boundaries, symbols, and overlays.

## Target Info

- **Serial / Boot ELF:** `SLPS_254.41` (NTSC, `VER = 1.03`)
- **Main ELF:** `0x0020001c` entry, `.text` at `0x00200000` (`0x1ac118` bytes), `.eh_frame` (`0x38a54` bytes), C++ RTTI/vtable sections, `.erx.lib`/`.erx.stub`, and `.DVP.overlay.*` VU microcode overlays
- **IOP Modules (`IRX/`):** `CDVDSTM`, `LIBSD`, `MCMAN`, `MCSERV`, `PADMAN`, `SDRDRV`, `SIO2MAN`, plus `SOUNDMAN.IRX` and `IOPRP300.IMG`
- **EE Overlays (`ERX/`):** `MISN/` (20 modules), `PLAYER00/` (20 modules), `PLAYER20/` (3 modules)
- **Data Archives:** `FILE1.BIN` – `FILE4.BIN`

## Progress

- [x] Repository and `.gitignore` setup
- [x] Extract and inspect PS2 ISO (`SYSTEM.CNF`, main ELF, `.IRX` modules)
- [ ] Analyze binary (functions, jump tables, overlays, SDK symbols)
- [ ] Set up MIPS R5900 static recompilation pipeline
- [ ] Implement EE kernel, IOP, and GS/VU HLE shims
- [ ] Native build and playable verification

## Goals

- Lift the PS2 Emotion Engine executable to portable C/C++.
- Implement lightweight HLE (High-Level Emulation) shims for EE kernel syscalls, IOP peripherals (controller, memory card, CDVD, SPU2), and Graphics Synthesizer / VU rendering.
- Build and run natively without full-system CPU emulation.
