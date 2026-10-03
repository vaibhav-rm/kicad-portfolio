# KiCad Projects Portfolio

A collection of PCB designs built with [KiCad](https://www.kicad.org/).
Each project lives in its own folder with schematic, PCB layout, and its own README.

Designed with **KiCad 10.0**.

## Projects

| # | Project | Description | Status |
|---|---------|-------------|--------|
| 01 | [AC to DC Converter](./AC%20t0%20DC%20Convertor/) | Mains-frequency AC to unregulated DC supply: bridge rectifier + bulk filter capacitor + power LED indicator, screw terminals for AC in / DC out. | 🟢 Complete |
| 02 | [Transformerless Power Supply](./Transforemerless%20power%20supply/) | Non-isolated capacitive-dropper 5 V supply: X-rated dropper cap → bridge → Zener clamp → LM7805 regulator, screw terminals for AC in / 5 V out. | 🟢 Complete |
| 03 | [Servo Tester](./Servo%20Tester/) | NE555-based hobby servo tester: 100 kΩ knob sweeps ~50 Hz PWM output, 3-pin servo header, power LED, 5 V in. | 🟢 Complete |

> Status legend: 🟢 Done · 🟡 In progress · 🔴 Planned

## Repository structure

```
.
├── "AC t0 DC Convertor"/         # Project 01
│   ├── *.kicad_sch               # Schematic
│   ├── *.kicad_pcb               # PCB layout
│   ├── *.kicad_pro               # Project file
│   ├── docs/                     # schematic.pdf + 3D renders
│   └── README.md                 # Project documentation (BOM, specs, build notes)
├── "Transforemerless power supply"/  # Project 02
│   ├── *.kicad_sch               # Schematic
│   ├── *.kicad_pcb               # PCB layout
│   ├── *.kicad_pro               # Project file
│   ├── docs/                     # schematic.pdf + 3D renders
│   └── README.md                 # Project documentation (BOM, specs, build notes)
├── "Servo Tester"/               # Project 03
│   ├── *.kicad_sch               # Schematic
│   ├── *.kicad_pcb               # PCB layout
│   ├── *.kicad_pro               # Project file
│   ├── docs/                     # schematic.pdf + 3D renders
│   └── README.md                 # Project documentation (BOM, specs, build notes)
└── README.md                     # This file
```

## How to open a project

1. Install KiCad 10.0 or newer.
2. Clone this repo:
   ```bash
   git clone git@github.com:vaibhav-rm/kicad-portfolio.git
   ```
3. Open the `.kicad_pro` file of the project you want inside KiCad.

## Conventions

- One folder per project.
- Every project has its own `README.md` with:
  - What the board does
  - Schematic overview / how it works
  - Bill of materials (BOM)
  - PCB details (size, layers)
  - Build / test notes
  - Current status and next steps
- KiCad `*-backups/` folders are design history and not part of the deliverables.

## Roadmap

- [x] Project 01 — AC to DC Converter
- [x] Project 02 — Transformerless Power Supply
- [x] Project 03 — Servo Tester
- [x] Schematic PDFs and 3D renders per project (`docs/`)
- [ ] Add Project 04

## License

TBD — add a license (e.g. CERN-OHL for hardware) if you plan to share or sell these designs.
