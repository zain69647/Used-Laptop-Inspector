# Used Laptop Inspector

A **portable Windows laptop inspection tool** designed to help buyers check a second-hand laptop before purchasing it.

The tool runs directly from a single `.bat` file and automatically collects hardware and system information, performs basic health checks, calculates an overall buyer score, and generates a professional **HTML inspection report**.

> **No installation required. No Python required. No third-party software required.**

---

## Features

### Battery Health
- Battery manufacturer and information
- Design capacity
- Full charge capacity
- Battery health percentage
- Battery cycle information where available
- Battery condition explanation
- Battery health visualization

### CPU Information
- Processor name
- CPU manufacturer
- CPU generation where detectable
- CPU series
- CPU suffix
- Cores and threads
- Maximum clock speed
- CPU category and usage explanation

### RAM Information
- Total RAM
- Number of memory modules
- RAM capacity per module
- Memory speed
- Manufacturer
- Part number
- Additional information where available

### Storage Inspection
- HDD / SSD detection
- SATA / NVMe information where available
- Drive model
- Capacity
- Interface
- Media type
- Storage health information where Windows exposes it

### GPU Information
- Graphics processor name
- Integrated / dedicated GPU identification
- VRAM where available
- Driver information
- Display resolution
- Refresh rate where available

### WinSAT Performance
The tool reads Windows System Assessment information where available:

- CPU score
- Memory score
- Graphics score
- Gaming graphics score
- Disk score
- Overall WinSPR score

Performance levels are presented in an easy-to-understand format.

### Windows & Security
- Windows edition
- Windows version
- Build number
- System architecture
- Activation status
- TPM information
- Secure Boot status

### BIOS & Motherboard
- Motherboard manufacturer
- Motherboard model
- BIOS version
- BIOS date
- Serial information where available

### Network
- Wi-Fi adapters
- Ethernet adapters
- Adapter status
- Link speed where available
- Network hardware information

---

## Buyer-Friendly Report

The generated HTML report is designed for **normal laptop buyers**, not just technicians.

Instead of displaying only raw technical data, the report explains:

- What each component does
- Why it matters
- Whether the detected specification is good or weak
- What the specification is suitable for
- What the buyer should check

The report also provides an overall buyer assessment:

```text
EXCELLENT
GOOD
FAIR
POOR
```

and can provide a recommendation such as:

```text
BUY
CHECK CAREFULLY
AVOID
```

The recommendation is intended as an inspection aid and should not replace physical testing.

---

## Physical Inspection Checklist

Some laptop problems cannot be detected reliably through software.

The report therefore includes a physical buyer checklist covering:

### Screen
- Dead pixels
- Brightness
- Flickering
- Scratches
- Backlight bleed
- Cracks

### Keyboard & Touchpad
- Individual keys
- Keyboard backlight
- Touchpad clicking
- Multi-touch

### Ports
- USB
- USB-C
- HDMI
- Audio jack
- Charging port
- SD card slot where applicable

### Camera & Audio
- Webcam
- Microphone
- Speakers
- Headphone jack

### Body
- Hinges
- Cracks
- Screws
- Rubber feet
- Physical damage
- Swelling
- Signs of liquid damage

### Charger
- Original charger
- Correct wattage
- Charging functionality

### Thermals
- Fan noise
- Excessive heat
- Unexpected shutdowns
- Possible thermal throttling

---

## How It Works

The project uses Windows built-in functionality.

```text
CHECK_LAPTOP.bat
        |
        v
Temporary inspection engine
        |
        v
Windows hardware/system information
        |
        v
Health & performance analysis
        |
        v
HTML report generation
        |
        v
Laptop_Report.html
```

The tool uses a temporary PowerShell inspection engine internally while keeping the user-facing tool as a **single BAT file**.

The temporary files are removed after the inspection where possible.

---

## Requirements

### Operating System

Primarily designed for:

- Windows 10
- Windows 11

Some information may not be available on older Windows versions or on systems where the manufacturer does not expose certain hardware information.

### No Installation Required

You do not need:

- Python
- Node.js
- Java
- .NET installation
- External benchmark software
- Third-party hardware monitoring software

The tool uses Windows components already available on supported systems.

---

## How to Use

1. Download `CHECK_LAPTOP.bat`.
2. Copy it to the laptop you want to inspect.
3. Double-click the BAT file.
4. Wait for the inspection to finish.
5. The HTML report will open automatically in your browser.
6. Review the report before purchasing the laptop.

For a second-hand laptop, it is recommended to run the inspection **before completing the purchase**.

---

## Important Limitations

This tool is an **inspection aid**, not a complete hardware diagnostic laboratory.

Software cannot reliably detect every physical problem.

For example, the tool may not be able to determine:

- Dead pixels reliably
- Hidden motherboard damage
- Intermittent keyboard problems
- Physical hinge damage
- Speaker distortion
- Loose ports
- Liquid damage that is not electronically detectable
- Exact screen panel technology in every laptop
- Actual charger authenticity
- Every SSD SMART attribute
- Every battery cycle count
- Thermal problems under every workload

Always perform the physical inspection checklist and test the laptop yourself.

> **Never rely solely on the software report when buying a used laptop.**

---

## CPU Suffix Guide

The report includes a simplified CPU suffix guide.

| Suffix | Typical Power | Common Use |
|---|---|---|
| U | Low | Office, travel, battery life |
| Y | Very Low | Basic portable systems |
| P | Medium | Thin/light performance |
| H | High | Gaming, editing, demanding work |
| HK | High | High-performance mobile |
| HX | Very High | Maximum laptop performance |
| K | High | Desktop gaming / overclocking |
| F | High | Desktop + dedicated GPU |
| KF | High | Gaming + dedicated GPU |
| T | Lower | Efficient desktop systems |

Exact capabilities depend on the specific processor model.

---

## WinSAT Score Guide

Where Windows provides WinSAT results:

| Score | General Level |
|---:|---|
| 9.0 – 9.9 | Excellent |
| 7.0 – 8.9 | Good |
| 5.0 – 6.9 | Entry-Level |
| Below 5.0 | Slow |

WinSAT is an older Windows performance assessment and should be treated as a **supporting indicator rather than a modern benchmark**.

---

## Battery Health Guide

Battery health is calculated using:

```text
Full Charge Capacity
-------------------- × 100
Design Capacity
```

General interpretation:

| Health | Condition |
|---:|---|
| 90–100% | Excellent |
| 80–89% | Good |
| 60–79% | Fair |
| Below 60% | Worn |

Actual battery life also depends on workload, screen brightness, processor power consumption, and other factors.

---

## Privacy

The tool is designed to perform the inspection locally on the Windows computer.

The generated report is stored locally and is not intentionally uploaded to an external server by the BAT itself.

---

## Project Status

**Working / Active Development**

The current version focuses on reliable Windows-based hardware inspection and a buyer-friendly HTML report.

Future improvements may include:

- More detailed SSD SMART information
- SSD temperature
- SSD power-on hours
- More accurate CPU generation detection
- DDR generation detection
- RAM slot availability
- Maximum supported RAM
- More detailed GPU classification
- Better display detection
- Additional thermal information
- More advanced battery analysis
- Expanded hardware compatibility checks

---

## Disclaimer

This project is provided for informational and educational purposes.

The inspection results are estimates based on information exposed by Windows and the computer's firmware/hardware.

A positive report does **not** guarantee that a used laptop is free from defects.

Always physically inspect and test a second-hand laptop before purchasing it.

---

## License

Choose a license appropriate for your project before publishing.

For example, you may use the **MIT License** if you want others to freely use, modify, and distribute the project.

---

## Author

**Zain Ali**

Built as a practical tool for inspecting second-hand laptops quickly and helping buyers understand what they are actually purchasing.
