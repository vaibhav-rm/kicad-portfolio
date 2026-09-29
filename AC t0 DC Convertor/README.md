# AC to DC Converter

Unregulated AC-to-DC power supply board: AC input → diode bridge rectifier →
bulk filter capacitor → DC output, with a power LED indicator.

> Folder name uses the original KiCad project name `AC t0 DC Convertor`
> (read: "AC to DC Converter").

## Features

- 2-pin screw terminal for AC input (e.g. transformer secondary)
- Full-wave bridge rectifier with 4 × 1N4007 diodes
- 1000 µF bulk filter capacitor for smoothing
- 2-pin screw terminal for DC output (`+VE` / GND)
- Power LED with series resistor as a power-on indicator
- Compact ~45 × 40 mm board

## How it works

```
AC IN (J1) ──► BRIDGE (D1–D4, 1N4007) ──► +VE ──► DC OUT (J2)
                        │                  │
                       GND            C1 1000 µF (across +VE/GND)
                                           │
                                     LED + R (power indicator)
```

1. The AC input is full-wave rectified by the 1N4007 bridge.
2. C1 (1000 µF) smooths the rectified waveform into unregulated DC.
3. The LED + series resistor branch lights when DC is present.

## Bill of materials (BOM)

| Qty | Designator | Value | Part | Footprint | Notes |
|-----|------------|-------|------|-----------|-------|
| 4 | D1–D4 | 1N4007 | Rectifier diode, 1 A / 1000 V | DO-41 | Bridge rectifier |
| 1 | C1 | 1000 µF | Aluminium electrolytic, mind voltage rating | Radial, D8.0 mm / P3.5 mm | Bulk filter — **verify voltage rating ≥ peak input** |
| 1 | D5 | LED | 5 mm LED | LED_D5.0mm | Power indicator |
| 1 | R1 | 10 kΩ | Resistor, THT axial | Axial DIN0204 | LED series resistor — **confirm value for your input voltage / LED current** |
| 1 | R2 | 2.2 kΩ | Resistor, THT axial | Axial DIN0204 | Second resistor in design — confirm placement/purpose |
| 2 | J1, J2 | Screw terminal 1×02 | 2-pin terminal block | Terminal block, P2.54 mm | AC in / DC out |

> The schematic still has a few unannotated symbols — run
> **Tools → Annotate Schematic** in KiCad and re-export the BOM before ordering parts.

## PCB details

- Designed in **KiCad 10.0**
- Board outline: ~45 × 40 mm rectangle with mounting holes
- Footprints placed; **routing is still in progress** (no copper tracks yet)
- Files:
  - `AC t0 DC Convertor.kicad_sch` — schematic
  - `AC t0 DC Convertor.kicad_pcb` — layout
  - `AC t0 DC Convertor.kicad_pro` — project file

## Getting started

1. Open `AC t0 DC Convertor.kicad_pro` in KiCad 10.0+.
2. Review/annotate the schematic, then run ERC until clean.
3. Finish PCB routing, pour GND if desired, then run DRC until clean.
4. Export Gerbers + drill files and a PDF schematic for fabrication.

## Testing

1. **Visual check:** correct diode/LED/capacitor polarity before powering.
2. **No-load test:** apply AC (start low, e.g. from an isolated transformer / variac),
   measure DC across `+VE`–GND with a multimeter.
3. **LED check:** indicator should light; if too dim/bright, adjust the series resistor.
4. **Load test:** apply the intended load and check ripple/sag and diode/capacitor temperature.

## Safety warning

This board works with AC voltages that can injure or kill.
Use an isolated source (e.g. transformer), a fuse on the input,
keep mains wiring off this board, and never probe it alone.
If this is meant to connect directly to mains, add proper fusing,
isolation, creepage/clearance, and enclosure — or redesign around
an off-the-shelf isolated module/transformer.

## Status

- [x] Schematic captured
- [x] Footprints assigned, board outline + mounting holes placed
- [x] Design complete

Possible follow-ups:

- [ ] Fully annotate schematic
- [ ] Export schematic PDF, 3D render, and Gerbers
- [ ] Physical build & test
