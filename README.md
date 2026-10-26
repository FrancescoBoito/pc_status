# ThinkPad System Status

A lightweight Bash command that displays useful system information in a clean terminal layout. Created for a Lenovo ThinkPad L14 Gen 1 running Linux Mint; it may also work on other Linux laptops.

## Features

- Battery charge, estimated health and cycle count, when available.
- Charge thresholds when exposed by the system.
- Temperature sensor readings.
- RAM and swap usage, root filesystem usage, and uptime.
- ThinkPad-inspired terminal colors; colors are disabled when output is redirected.

The command reads system information and does not change settings. Sensor availability depends on hardware and drivers.

## Requirements

Bash, `upower`, `lm-sensors`, and standard Linux utilities such as `free`, `df`, `awk`, `grep`, and `sed`. TLP is optional for detailed battery information.

On Linux Mint or Ubuntu:

```bash
sudo apt update
sudo apt install upower lm-sensors
```

## Installation

```bash
git clone https://github.com/FrancescoBoito/thinkpad-system-status.git
cd thinkpad-system-status
mkdir -p ~/.local/bin
cp tpad ~/.local/bin/tpad
chmod +x ~/.local/bin/tpad
```

Open a new terminal and run `tpad`. If the command is not found, add the directory to your Bash PATH:

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

## Usage

```bash
tpad
```

For more detailed battery and charge threshold information, if TLP is installed:

```bash
sudo tlp-stat -b
```

The charge threshold section checks `BAT0`; your battery may use a different identifier. Disk usage refers to the Linux root filesystem.
