# CLAUDE.md

This file provides guidance to AI assistants when working with code in this repository.

## Overview

This is an OpenClaw skill that converts ASCII/Unicode QR code block matrices (terminal output) into high-definition PNG images. The primary use case is refining QR codes captured from CLI tools that output block characters (`█`, `▀`, `▄`).

## Commands

### Run Refinement
```bash
python3 scripts/cli_qr_refiner.py <input_txt_path> <output_png_path> [scale]
```

- `scale` is optional (default: 10), controls pixel size per character cell

## Architecture

The script `scripts/cli_qr_refiner.py` handles:
1. Reading raw ASCII/Unicode QR block data from a text file
2. Auto-detecting matrix dimensions
3. Rendering to PNG via PIL with:
   - `█` → full black pixel block
   - `▀` → upper half black block
   - `▄` → lower half black block
   - scale factor of 10x (each character becomes 10×20 pixels by default)

## Dependencies
- Python 3 (no external packages — uses built-in PIL/Pillow)

## File Structure
```
├── SKILL.md              # OpenClaw skill manifest
├── scripts/
│   └── cli_qr_refiner.py # Main rendering logic
├── README.md             # User-facing documentation
├── CLAUDE.md             # This file
└── .gitignore            # Python artifacts to ignore
```
