# dsPIC30F4011 DIP-40 Development Board  
*A through-hole, single-supply platform for mixed-signal DSP labs*

[![KiCad 8.x](https://img.shields.io/badge/KiCad-8.x-blue.svg)](https://kicad.org)  
[![Latest Revision D](https://img.shields.io/badge/hardware-Rev%20D-orange.svg)](#hardware-revisions)  
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> Compact, **breadboard-friendly** board built around Microchip’s  
> **dsPIC30F4011 (DIP-40)**. Ideal for university courses and hobbyists who need a low-cost, fully-THT solution for real-time DSP, motor-control, or instrumentation projects.

---

## 📑 Table of Contents
1. [Key Features (Rev D)](#key-features-rev-d)  
2. [Hardware Revisions](#hardware-revisions)  
3. [Folder Structure](#folder-structure)  
4. [Quick Start](#quick-start)  
5. [Bill of Materials](#bill-of-materials)  
6. [Contributing](#contributing)  
7. [License](#license)  
8. [Resumen rápido en español](#resumen-rápido-en-español)

---

## Key Features (Rev D)

| Block            | Details                                                                                                     |
|------------------|-------------------------------------------------------------------------------------------------------------|
| **Power**        | 12 V DC barrel jack → **on-board 5 V LDO** (LM7805)                                                         |
| **CPU**          | **dsPIC30F4011**, 30 MIPS, **socket pads widened** for easy solder/rework                                    |
| **Clock**        |  precise UART/DSP timing                                                                                     |
| **Reset**        | Single **RC + Schmitt trigger** → faster boot, ~50 % parts count cut                                         |
| **ICSP**         | Standard 6-pin header (Pickit 3/4 compatible)                                                               |
| **Service**      | **Bridge jumpers** isolate power, ICSP, and analog rails → safe bring-up / troubleshooting                   |
| **Silkscreen**   | Pin name on **every** MCU pad + labelled test points                                                        |
| **Form Factor**  | 52 mm × 45 mm PCB (≈18 % smaller than Rev B) — fits 70 mm breadboards                                        |

*Full schematic, 3-D renders, PDFs, and Gerbers live in `/hardware/Rev_D/`.*

---

## Hardware Revisions

| Rev | Focus                      | Major Changes                                                                                                          |
|-----|----------------------------|------------------------------------------------------------------------------------------------------------------------|
| **B** | First production           | Base THT design, 12 V→5 V regulation, full silkscreen                                                                  |
| **C** | Bug-fix & size reduction  | Fixed reversed barrel polarity, wired V<sub>REF±</sub>; **PCB shrunk** 63 × 52 mm → 52 × 45 mm                          |
| **D** | Serviceability & accuracy | Simplified reset, **larger socket pads**, bridge jumpers, **crystal oscillator added**                                 |

*Older spins remain for reference; **Rev D** is the recommended build.*

---

## Folder Structure
```text
.
├── hardware/         # KiCad 8 projects
│   ├── Rev_B/
│   ├── Rev_C/
│   └── Rev_D/
├── firmware/         # MPLAB X XC16 demo code (blinky, UART loop-back, FIR demo)
├── docs/             # Schematics (PDF), BOMs (CSV/XLSX), 3-D STEP
└── README.md
```

---

## Quick Start

### 1 · Clone & Open Hardware

```bash
git clone https://github.com/<your-org>/dsPIC30F4011-THT.git
cd dsPIC30F4011-THT/hardware/Rev_D
kicad Rev_D.kicad_pro    # KiCad ≥ 8.0
```

### 2 · Generate Gerbers

KiCad → **File ▸ Plot** → select *Gerber* + *Drill*; zip and send to JLCPCB / PCBWay / OSH Park.

### 3 · Assemble

All parts are **through-hole**; ideal for hand-soldering or wave machines.
*Tip :* keep bridge jumpers **open** on first power-up.

### 4 · Flash the Demo

TBD

---

## Bill of Materials (excerpt)

| Qty | Designator | Part & Link         | Note                 |
| --- | ---------- | ------------------- | -------------------- |
| 1   | U1         | dsPIC30F4011-I/P    | 40-pin DIP, 30 MIPS  |
| 1   | X1         | Crystal 7 .3728 MHz | HC-49S               |
| 2   | C7, C8     | 22 pF NP0           | Crystal load caps    |
| 1   | IC1        | LM7805              | TO-220, 1 A          |
| 8   | C1…C8      | 100 nF MLCC         | Decoupling (per VDD) |

*See* `docs/BOM_Rev_D.xlsx` *for the full list with supplier SKUs.*

---

## Contributing
TBD

Bug reports and board mods are welcome!

---

## License

All hardware, firmware, and documents are released under the **MIT License**.
See the [LICENSE](LICENSE) file for details.

---

## Resumen rápido (español)

* Placa educativa **THT** con **dsPIC30F4011**.
* Rev D añade cristal, jumpers de aislamiento y pads más amplios.
* Archivos KiCad 8 en `/hardware/Rev_D/`; BOM completa en `docs/`.
* Programación vía ICSP con Pickit 3/4.

¡Felices prototipos! 🎉
