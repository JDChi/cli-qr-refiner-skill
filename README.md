# CLI-QR-Refiner

A specialized tool for converting ASCII/Unicode QR code block matrices from CLI terminal outputs into crystal-clear, scannable PNG images.

## Features

- **Block Recognition**: Automatically interprets `█` (full), `▀` (upper), and `▄` (lower) block characters
- **Pixel-Perfect Scaling**: Renders with vector-like precision to ensure zero scanning failures
- **Zero Dependencies**: Built on Python 3 + PIL (pre-installed on most systems)
- **Headless Optimized**: Designed for server-side environments where terminal displays are unreliable

## Prerequisites

- Python 3 (no external packages required — PIL/Pillow is built-in)

## Usage

```bash
python3 scripts/cli_qr_refiner.py <input_txt_path> <output_png_path> [scale]
```

- `scale` is optional (default: 10), controls pixel size per character cell

## Example

### Input (ASCII/Unicode)
```
██████████████  ██  ██████████████
██          ██  ██  ██          ██
██  ██████  ██      ██  ██████  ██
```

Save this to a text file and run:

```bash
python3 scripts/cli_qr_refiner.py qr_source.txt qr_output.png
```

### Output

A high-definition PNG file ready for any QR code scanning app.

## When to Use

- A CLI tool (WeChat, Aliyun, NPM, etc.) outputs a block-character matrix intended for scanning
- Scanning failures due to terminal alignment, line-height, or font rendering issues
