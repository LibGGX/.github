# LibGGX Project - AI README Draft, May be gibberish

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Build]()]()

LibGGX is the next-generation toolkit for Xbox 360 NAND manipulation, research, and development. Built from the ground up in native Rust, it provides a high-performance, memory-safe alternative to legacy tools. Whether you are building donor NANDs for RGH3, extracting assets from system updates, or implementing advanced hypervisor patches, LibGGX offers a modular and extensible architecture to handle the most complex tasks with ease.

## Project Structure

This workspace orchestrates several specialized crates, each designed for a specific layer of the Xbox 360 ecosystem:

- **[libggx-cli](libggx-cli)**: The primary entry point. A unified command-line interface that orchestrates all underlying crates for NAND building, patching, and extraction.
- **[libggx-nand](libggx-nand)**: A comprehensive NAND disassembler and builder with support for surgical injection, bad block remapping, and automatic ECC generation.
- **[libggx-patcher](libggx-patcher)** (Bilateral): A 3-stage patching engine implementing the GSP (GGX Signature Patch) 1.0/2.0 specifications with instruction-aware matching.
- **[libggx-crypto](libggx-crypto)**: Native Rust implementation of Xbox 360 cryptographic primitives, from the proprietary SMC multiplier cipher to RC4/HMAC-SHA1.
- **[libggx-gfc](libggx-gfc)**: Implementation of the Generic File Container (GFC/FlashFS) and Xbox File Table (XFT) formats for dashboard partition construction.
- **[libggx-stfs](libggx-stfs)**: STFS (`CON`/`LIVE`) and System Update (SU) blob parsing for direct bootloader extraction from official packages.
- **[libggx-compression](libggx-compression)**: High-speed, native LZX and XPress compression routines essential for dashboard asset management.
- **[libggx-commands](libggx-commands)**: The orchestration and FFI layer, providing a bridge for C# and C++ applications (like J-Runner) to leverage LibGGX.

## Getting Started

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (latest stable)
- `cargo`

### Building

To build the entire project:

```bash
cargo build --release
```

## License

Parts of this project (Keychain) are licensed under the GNU Lesser General Public License Version 3.0
