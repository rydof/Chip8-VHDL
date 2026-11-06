# Chip8-VHDL

A hardware implementation of a CHIP-8 virtual machine, written in VHDL and built with Xilinx Vivado. It targets the Digilent Basys 3 board (Xilinx Artix-7 FPGA).

**Status:** work in progress.

## About

CHIP-8 is a small virtual machine from the 1970s, originally used to run simple games. Instead of emulating it in software, this project describes the machine directly in hardware, so the whole design runs on the FPGA itself.

## Features

- CHIP-8 CPU core built as an FSM, with opcode support that has grown over the project, including `RND` (with its own random number entity), `RET`, BCD conversion (`LD_BCD_REG`), `ADD_I_REG`, the register load/store opcodes (`LD_I_REGS`, `LD_REGS_I`) and the key-skip opcodes (`SKP_KEY`)
- VGA output with a configurable `SCALE_FACTOR` and a graphics unit that draws the CHIP-8 display
- Keypad input through a PMOD keypad on the Basys 3
- Several ROMs stored in RAM, selectable with the switches on the board
- Real-time register monitoring on the seven-segment display
- Opcode testbench with a saved waveform setup (`tb_opcodes_behav.wcfg`)

## What you need

- A Digilent Basys 3 board
- A VGA monitor
- A PMOD keypad
- Xilinx Vivado

## Getting started

1. Clone the repository:
   ```bash
   git clone https://github.com/rydof/Chip8-VHDL.git
   ```
2. Open `Chip8.xpr` in Vivado.
3. Run a behavioral simulation to check the opcodes.
4. Synthesize, implement and generate the bitstream, then program the Basys 3 board.
5. Use the switches to pick a ROM and the keypad to play.

## Repository layout

- `Chip8.srcs/` - Vivado project sources
- `Chip8.xpr` - Vivado project file
- `tb_opcodes_behav.wcfg` - waveform configuration for the opcode testbench simulation

## Credits

Made by [@rydof](https://github.com/rydof) and [@frudex](https://github.com/frudex).

## License

MIT, see [LICENSE](LICENSE).
