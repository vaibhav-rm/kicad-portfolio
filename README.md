# KiCad Projects Portfolio

A collection of PCB designs built with [KiCad](https://www.kicad.org/).
Each project lives in its own folder with schematic, PCB layout, and its own README.

Designed with **KiCad 10.0**.

## Projects

| # | Project | Description | Status |
|---|---------|-------------|--------|
| 01 | [AC to DC Converter](./AC%20t0%20DC%20Convertor/) | Mains-frequency AC to unregulated DC supply: bridge rectifier + bulk filter capacitor + power LED indicator, screw terminals for AC in / DC out. | 🟡 In progress — schematic done, PCB layout pending routing |

> Status legend: 🟢 Done · 🟡 In progress · 🔴 Planned

## Repository structure

```
.
├── "AC t0 DC Convertor"/   # Project 01
│   ├── *.kicad_sch         # Schematic
│   ├── *.kicad_pcb         # PCB layout
│   ├── *.kicad_pro         # Project file
│   └── README.md           # Project documentation (BOM, specs, build notes)
└── README.md               # This file
```

## How to open a project

1. Install KiCad 10.0 or newer.
2. Clone this repo:
   ```bash
   git clone <repo-url>
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

- [ ] Finish routing Project 01 and run DRC clean
- [ ] Add schematic/PDF exports and 3D renders per project
- [ ] Add Gerbers for fabrication per project
- [ ] Add Project 02

## License

TBD — add a license (e.g. CERN-OHL for hardware) if you plan to share or sell these designs.
