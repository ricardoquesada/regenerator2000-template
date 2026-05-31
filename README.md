# Regenerator 2000 Template Project

Welcome to the **Regenerator 2000 Template Project**!
This project is a template designed to help you start a Commodore 8-bit
disassembly quickly and seamlessly using **Regenerator 2000**.

It comes pre-configured with all the necessary agent skills and IDE permissions,
allowing Claude and Antigravity to interact with the **Regenerator 2000 MCP server**
out of the box.

---

## Features & Pre-configuration

- **Ready-to-use Agent Skills**:
  - Located under `.agent/skills/` (for Antigravity) and `.claude/skills/` (for Claude).
  - These skills include program, block, basic, routine, and symbol analysis orchestrations to help AI assistants analyze disassembled MOS 6502 code and target-system details.
- **Pre-approved MCP Permissions**:
  - Configured in `.vscode/settings.json`, granting Claude and Antigravity permissions to call the `Regenerator2000` MCP server (`Regenerator2000/*`) without repeatedly prompting you for authorization.

---

## Installation Instructions

For full documentation, visit the official [Regenerator 2000 Installation & Usage Docs](https://regenerator2000.readthedocs.io/en/latest/install/).

### 1. Pre-compiled Binaries

You can download pre-compiled binaries for Linux, macOS, and Windows directly from the GitHub releases page:
👉 [Latest Regenerator 2000 Releases](https://github.com/ricardoquesada/regenerator2000/releases/latest)

### 2. Install via Crates.io

If you have [Rust and Cargo](https://rustup.rs/) installed, you can install the tool globally:

```bash
cargo install regenerator2000
```

### 3. Install from Source

To clone and compile the repository manually:

```bash
git clone https://github.com/ricardoquesada/regenerator2000.git
cd regenerator2000
cargo install --path .
```

---

## Running Regenerator 2000

Start the interactive terminal UI (TUI) by providing a target file:

```bash
regenerator2000 [OPTIONS] [FILE]
```

### Quick Example with `bin/c64_moving_tubes_lxt.d64`

This template repository includes a sample Commodore 64 disk image `bin/c64_moving_tubes_lxt.d64`
for you to test and start playing with disassemblies immediately.

To run the interactive TUI with this example, with the MCP server enabled:

```bash
regenerator2000 --mcp-server bin/c64_moving_tubes_lxt.d64
```

_Note: Since `.d64` is a disk container, Regenerator 2000 will display a menu allowing you to
select which `.prg` program inside the disk you would like to load and disassemble._

---

## Supported File Formats

Regenerator 2000 natively supports:

- `.prg` - Commodore 8-bit program files (automatically parses SYS entry points).
- `.crt` - Commodore 64 cartridge files (supports bank selection).
- `.d64`, `.d71`, `.d81` - C64/C128 disk images (allows selecting `.prg` programs).
- `.t64` - Tape images.
- `.vsf` - VICE snapshot files (extracts 64KB RAM and sets PC as entry point).
- `.dis65` - 6502bench SourceGen project files.
- `.bin`, `.raw` - Pure raw binary files.
- `.regen2000proj` - Regenerator 2000 project files.

## Recommended Terminals

For the best text user interface rendering and full keyboard shortcut support, we highly recommend using a modern terminal emulator:

- **macOS**: Ghostty, iTerm2, Alacritty, Kitty, WezTerm
- **Windows**: Windows Terminal, Alacritty, WezTerm
- **Linux**: Ghostty, Alacritty, Kitty, WezTerm
