# game-of-life

Conway’s Game of Life (2D) und Millen/BYTE 1D-Life — als Python-Terminal-App und Commodore-BASIC-Ports (C64, C16/Plus4, C128, MEGA65).

## Programme

| Plattform | 2D | 1D | Raster | Hinweise |
|-----------|----|----|--------|----------|
| PC | [`pc/2d_game_of_life.py`](pc/2d_game_of_life.py) | — | Terminalgröße | Editor, Muster, mehrere Regelwerke |
| C64 | [`c64/2d_game_of_life.bas`](c64/2d_game_of_life.bas) | [`c64/1d_game_of_life.bas`](c64/1d_game_of_life.bas) | 40×23 | 2D in BASIC extrem langsam |
| C16 / Plus4 | [`c16/2d_game_of_life.bas`](c16/2d_game_of_life.bas) | [`c16/1d_game_of_life.bas`](c16/1d_game_of_life.bas) | 40×23 | TED; Boot-Lila (`COLOR 1,15,6`) |
| C128 VIC-II | [`c128/2d_game_of_life_vic2-40.bas`](c128/2d_game_of_life_vic2-40.bas) | [`c128/1d_game_of_life_vic2-40.bas`](c128/1d_game_of_life_vic2-40.bas) | 40×23 | Nur 40 Spalten; `SLOW` (nicht `FAST`) |
| C128 VDC | [`c128/2d_game_of_life_vdc-80.bas`](c128/2d_game_of_life_vdc-80.bas) | [`c128/1d_game_of_life_vdc-80.bas`](c128/1d_game_of_life_vdc-80.bas) | 80×23 | `FAST`; Emulator: 80col/VDC-Fenster |
| MEGA65 | [`mega65/2d_game_of_life_80.bas`](mega65/2d_game_of_life_80.bas) | [`mega65/1d_game_of_life_80.bas`](mega65/1d_game_of_life_80.bas) | 80×23 | Hardware getestet (`SPEED`, `T@&`); auch als [`.prg`](mega65/2d_game_of_life_80.prg) / [`.d81`](mega65/2d_game_of_life.d81) |

Auf C64/C16/C128 ist 2D-Life in reinem BASIC praktisch nur als Demo nutzbar. MEGA65 läuft mit `SPEED` brauchbar.

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

Plattformspezifisch:

- **C128 VIC-II:** `SLOW` behalten — `FAST` macht den VIC-Screen schwarz.
- **C128 VDC:** zuerst 80-Spalten-/VDC-Fenster, dann laden.
- **C16:** Screen `3072`, Color `2048`.
- **MEGA65:** schaltet bei Bedarf auf 80 Spalten; Diskimage enthält das 2D-Programm.

## Lizenz

Keine Lizenzdatei im Repository — bei Weitergabe bitte eine passende Lizenz ergänzen oder mit dem Maintainer klären.
