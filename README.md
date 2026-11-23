# BB400 Eurorack Power Breakout

A minimal, U-shaped Eurorack power breakout PCB designed to plug directly into the power rails of a **BusBoard BB400** (400-tie-point) solderless breadboard without blocking the main prototyping area.

> **Status (`v0.1` - Ready for Prototype Fabrication):** Schematic and 2-layer PCB layout pass ERC and DRC with 0 errors and 0 warnings. Rail header spacing (`47.0 mm` outer-to-outer) has been caliper-verified against a physical BusBoard BB400. *(Hardware prototype test pending.)*

<!-- Optional: add your KiCad 3D render PNG here once exported
![3D Render](docs/render_top.png)
-->

## Features

- Connects to any standard **16-pin Eurorack power supply** (`+12V`, `-12V`, `+5V`, `GND`) via a keyed shrouded IDC header
- **U-shaped outline** (`55 x 32 mm`) sits cleanly off the end of the `54 mm` wide BB400 and leaves all 30 tie-point rows unobstructed
- **250 mA resettable PTC polyfuses** on all three voltage rails to protect your Eurorack case PSU from accidental breadboard shorts
- **Local rail filtering** (`10 uF` electrolytic + `100 nF` ceramic) on `+12V`, `+5V`, and `-12V`
- **2x2 underside male headers** (`47.0 mm` outer-to-outer) on each arm for a solid mechanical grip in the breadboard rails
- 100% through-hole (THT) components for easy hand-soldering

## Breadboard Rail Mapping

- **Left Arm (`J2`):** Outer rail (`+` red) = **`+12V`** | Inner rail (`-` black) = **`GND`**
- **Right Arm (`J3`):** Inner rail (`-` black) = **`-12V`** | Outer rail (`+` red) = **`+5V`**

## Bill of Materials (BOM)

| Ref | Qty | Value / Description | Footprint / Notes |
| :--- | :---: | :--- | :--- |
| `J1` | 1 | 2x8 (16-pin) Shrouded IDC Header, 2.54 mm | Vertical, keyed (Eurorack power) |
| `J2`, `J3` | 2 | 2x2 Male Pin Header, 2.54 mm | Mounted on **bottom** (`B.Cu`) |
| `F1`-`F3` | 3 | 250 mA Resettable PTC Polyfuse (30-60 V radial) | 5.1 mm pitch (e.g., Bourns `MF-R025` / Littelfuse `RXEF025`) |
| `C1`-`C3` | 3 | 10 uF, 25-35 V Electrolytic Capacitor | Radial, 5 mm dia, 2.0 mm pitch *(note reversed polarity on `C3` for `-12V`)* |
| `C4`-`C6` | 3 | 100 nF (0.1 uF), 50 V Ceramic Capacitor | Radial, 5.0 mm pitch |

## Assembly Notes

1. Solder all top-side components (`J1`, `F1`-`F3`, `C1`-`C6`) first. **Double-check `C3` polarity** - on the `-12V` rail, its `+` lead connects to `GND` and its `-` lead connects to `-12V`.
2. For effortless alignment, plug the `J2` and `J3` male pin headers into your BB400's power rails first, drop the PCB onto the pins, and solder them in place.
3. Verify `+12V`, `+5V`, and `-12V` with a multimeter before powering a circuit on the breadboard.

## Fabrication

- **Layers:** 2-layer FR4, 1.6 mm thickness, 1 oz copper
- **Designed in:** KiCad 10
- **OSH Park:** Upload the `.kicad_pcb` file directly.

## License

(c) 2026 William Chrapcynski - Licensed under **CC BY-NC-SA 4.0** (Attribution-NonCommercial-ShareAlike 4.0 International).