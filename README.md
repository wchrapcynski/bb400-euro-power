# BB400 Eurorack Power Breakout

<img width="978" height="713" alt="image" src="https://github.com/user-attachments/assets/cdc950c7-37f7-4d49-bedc-84f2ca4e07d3" />

A minimal, U-shaped Eurorack power breakout PCB designed to plug directly into the power rails of a **BusBoard BB400** (400-tie-point) solderless breadboard without blocking the main prototyping area.

> **Status (`v0.1` — Work in Progress):** Schematic and PCB layout are complete and pass ERC/DRC. Final X-spacing of the breadboard rail headers (`J2`/`J3`) is pending caliper verification against a physical BB400 before the first prototype fabrication run.

## Features

- Connects to any standard **16-pin Eurorack power supply** (`+12V`, `-12V`, `+5V`, `GND`) via a keyed shrouded IDC header
- **U-shaped outline** (`55 × 32 mm`) sits cleanly off the end of the BB400 and leaves all 30 tie-point rows unobstructed
- **250 mA resettable PTC polyfuses** on all three voltage rails to protect your Eurorack case PSU from accidental breadboard shorts
- **Local rail filtering** (`10 µF` electrolytic + `100 nF` ceramic) on `+12V`, `+5V`, and `-12V`
- **2×2 underside male headers** on each arm for a solid mechanical grip in the breadboard rails
- 100% through-hole (THT) components for easy hand-soldering

## Breadboard Rail Mapping

- **Left Arm (`J2`):** Outer rail (`+` red) = **`+12V`** · Inner rail (`-` black) = **`GND`**
- **Right Arm (`J3`):** Inner rail (`-` black) = **`-12V`** · Outer rail (`+` red) = **`+5V`**

## Bill of Materials (BOM)

| Ref | Qty | Value / Description | Footprint / Notes |
| :--- | :---: | :--- | :--- |
| `J1` | 1 | 2×8 (16-pin) Shrouded IDC Header, 2.54 mm | Vertical, keyed (Eurorack power) |
| `J2`, `J3` | 2 | 2×2 Male Pin Header, 2.54 mm | Mounted on **bottom** (`B.Cu`) |
| `F1`–`F3` | 3 | 250 mA Resettable PTC Polyfuse (30–60 V radial) | 5.1 mm pitch (e.g., Bourns `MF-R025` / Littelfuse `RXEF025`) |
| `C1`–`C3` | 3 | 10 µF, 25–35 V Electrolytic Capacitor | Radial, 5 mm dia, 2.0 mm pitch *(note reversed polarity on `C3` for `-12V`)* |
| `C4`–`C6` | 3 | 100 nF (0.1 µF), 50 V Ceramic Capacitor | Radial, 5.0 mm pitch |

## Assembly Notes

1. Solder all top-side components (`J1`, `F1`–`F3`, `C1`–`C6`) first. **Double-check `C3` polarity**—its `+` lead connects to `GND` and `-` lead connects to `-12V`.
2. To ensure perfect alignment, plug the `J2` and `J3` male pin headers into your BB400's power rails first, drop the PCB onto the pins, and solder them in place.
3. Verify rail voltages with a multimeter before connecting any circuit on the breadboard.

## Built With

- Designed in **KiCad 10**

## License

© William Chrapcynski — Licensed under **CC BY-NC-SA 4.0** (Attribution-NonCommercial-ShareAlike 4.0 International).
