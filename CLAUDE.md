# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an OpenClaw skill that converts ASCII/Unicode QR code block matrices (terminal output) into high-definition PNG images. The primary use case is refining QR codes captured from CLI tools that output block characters (`█`, `▀`, `▄`).

## Commands

### Install Dependencies
```bash
npm install canvas
```

### Run Refinement
```bash
node scripts/cli_qr_refiner.js <input_txt_path> <output_png_path>
```

## Architecture

The single script `scripts/cli_qr_refiner.js` handles:
1. Reading raw ASCII/Unicode QR block data from a text file
2. Auto-detecting matrix dimensions
3. Rendering to PNG via the `canvas` library with:
   - `█` → full black pixel block
   - `▀` → upper half black block
   - `▄` → lower half black block
   - scale factor of 10x (each character becomes 10x20 pixels)

## File Structure
```
├── SKILL.md          # OpenClaw skill manifest
├── scripts/
│   └── cli_qr_refiner.js  # Main rendering logic
└── CLAUDE.md         # This file
```
