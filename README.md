# game-of-life

Conway’s Game of Life (2D) und Millen/BYTE 1D-Life — als Python-Terminal-App und Commodore-BASIC-Ports (C64, C16/Plus4, C128, MEGA65).

## Programme

### 2D

- PC: [`pc/2d_game_of_life.py`](pc/2d_game_of_life.py)
- C64: [`c64/2d_game_of_life.bas`](c64/2d_game_of_life.bas)
- C16 / Plus4: [`c16/2d_game_of_life.bas`](c16/2d_game_of_life.bas)
- C128 VIC-II: [`c128/2d_game_of_life_vic2-40.bas`](c128/2d_game_of_life_vic2-40.bas)
- C128 VDC: [`c128/2d_game_of_life_vdc-80.bas`](c128/2d_game_of_life_vdc-80.bas)
- MEGA65: [`mega65/2d_game_of_life_80.bas`](mega65/2d_game_of_life_80.bas) ([`.prg`](mega65/2d_game_of_life_80.prg), [`.d81`](mega65/2d_game_of_life.d81))

### 1D

- C64: [`c64/1d_game_of_life.bas`](c64/1d_game_of_life.bas)
- C16 / Plus4: [`c16/1d_game_of_life.bas`](c16/1d_game_of_life.bas)
- C128 VIC-II: [`c128/1d_game_of_life_vic2-40.bas`](c128/1d_game_of_life_vic2-40.bas)
- C128 VDC: [`c128/1d_game_of_life_vdc-80.bas`](c128/1d_game_of_life_vdc-80.bas)

Die BASIC-Ports sind langsam.

## Regeln (BASIC-Ports)

**2D — Conway B3/S23:** Simultanes Update (Doppelpuffer), Zufallsstart 15–20 % plus zwei Glider. Statuszeile `POP` / `GEN`. Neustart nach 20 Generationen.

**1D — Millen/BYTE-Life** ([jonmillen.com/1dlife](https://jonmillen.com/1dlife/index.html)): Nachbarschaft `YYXYY` (Geburt bei 2\|3, Überleben bei 2\|4 Y-Nachbarn), Wrap-Ring, Evolution-Ansicht (jede Generation eine Zeile). Seed 28–35 %. Status `POP` / `SEED` / `GEN`. Neustart nach 20 Generationen.

## PC

Python 3.8+, `curses` (Windows: `pip install windows-curses`).

```bash
python3 pc/2d_game_of_life.py
```

Interaktiver Editor: Musterbibliothek, Regelwerke (B/S), Torus, Zellalter, Statistik. Raster folgt der Terminalgröße. Hilfe im Programm mit `H` / `?`.

| Taste | Aktion |
|-------|--------|
| Leertaste | Pause / Weiter |
| `.` / `N` | Ein Schritt |
| `P` / `[` `]` | Muster platzieren / wählen |
| `O` | Regelwerk wechseln |
| `T` | Torus an/aus |
| `Q` / ESC | Beenden |

## Commodore / MEGA65

BASIC-Quellen laden und `RUN`. Emulatoren: VICE (`x64`, `xplus4`, `x128`), für MEGA65 die passende Runtime bzw. Hardware.

## Lizenz

Keine Lizenzdatei im Repository — bei Weitergabe bitte eine passende Lizenz ergänzen oder mit dem Maintainer klären.
