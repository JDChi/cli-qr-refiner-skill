# CLI-QR-Refiner

A specialized tool for converting ASCII/Unicode QR code block matrices from CLI terminal outputs into crystal-clear, scannable PNG images.

## Features

- **Block Recognition**: Automatically interprets `█` (full), `▀` (upper), and `▄` (lower) block characters
- **Pixel-Perfect Scaling**: Renders with vector-like precision to ensure zero scanning failures
- **Headless Optimized**: Designed for server-side environments where terminal displays are unreliable

## Prerequisites

- Node.js v16+
- `canvas` npm package

## Installation

```bash
npm install canvas
```

## Usage

```bash
node scripts/cli_qr_refiner.js <input_txt_path> <output_png_path>
```

## Example

### Input (ASCII/Unicode)
```
██████████████  ██  ██████████████
██          ██  ██  ██          ██
██  ██████  ██      ██  ██████  ██
```

Save this to a text file and run:

```bash
node scripts/cli_qr_refiner.js qr_source.txt qr_output.png
```

### Output

A high-definition PNG file ready for any QR code scanning app.

## When to Use

- A CLI tool (WeChat, Aliyun, NPM, etc.) outputs a block-character matrix intended for scanning
- Scanning failures due to terminal alignment, line-height, or font rendering issues
