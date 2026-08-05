# game-of-life

**Conway’s Game of Life** und **1D Life** (Millen/BYTE) — PC (Python/`curses`) sowie Commodore-BASIC-Ports (C64, C16/Plus4, C128, MEGA65).

## Übersicht

| Plattform | Programm | Beschreibung |
|-----------|----------|--------------|
| PC | [2D Game of Life](pc/2d_game_of_life.py) | Terminal-Editor, Muster, mehrere Regelwerke |
| C64 | [2D Game of Life](c64/2d_game_of_life.bas) | 40×23; **extrem langsam** |
| C64 | [1D Game of Life](c64/1d_game_of_life.bas) | Millen/BYTE 1D-Life, Evolution-Ansicht |
| C16 | [2D Game of Life](c16/2d_game_of_life.bas) | TED; **extrem langsam** |
| C16 | [1D Game of Life](c16/1d_game_of_life.bas) | Millen/BYTE 1D-Life, Evolution-Ansicht |
| C128 | [2D Game of Life (VIC-II)](c128/2d_game_of_life_vic2-40.bas) | 40 Spalten; **extrem langsam** |
| C128 | [1D Game of Life (VIC-II)](c128/1d_game_of_life_vic2-40.bas) | 1D-Life, 40 Spalten VIC-II |
| C128 | [2D Game of Life (VDC)](c128/2d_game_of_life_vdc-80.bas) | 80 Spalten VDC; **extrem langsam** |
| C128 | [1D Game of Life (VDC)](c128/1d_game_of_life_vdc-80.bas) | 1D-Life, 80 Spalten VDC |
| MEGA65 | [2D Game of Life](mega65/2d_game_of_life_80.bas) | 80 Spalten; **auf Hardware getestet** |
| MEGA65 | [1D Game of Life](mega65/1d_game_of_life_80.bas) | 1D-Life, 80 Spalten, Evolution-Ansicht |

## Verzeichnisstruktur

```
game-of-life/
├── README.md
├── pc/
│   └── 2d_game_of_life.py        # Python 3 / curses
├── c64/
│   ├── 2d_game_of_life.bas
│   └── 1d_game_of_life.bas
├── c16/
│   ├── 2d_game_of_life.bas
│   └── 1d_game_of_life.bas
├── c128/
│   ├── 2d_game_of_life_vic2-40.bas
│   ├── 1d_game_of_life_vic2-40.bas
│   ├── 2d_game_of_life_vdc-80.bas
│   └── 1d_game_of_life_vdc-80.bas
└── mega65/
    ├── 2d_game_of_life_80.bas
    ├── 1d_game_of_life_80.bas
    ├── 2d_game_of_life_80.prg
    └── 2d_game_of_life.d81
```

---

## Regeln

**2D:** Conway B3/S23, simultanes Update (Doppelpuffer), Zufallsstart **15–20 %** plus zwei Glider; Status `POP`/`GEN`; Neustart nach **20** Gen. Auf C64/C16/C128 **extrem langsam**; auf dem **MEGA65 getestet** (`SPEED`).

**1D:** Millen/BYTE-Life ([jonmillen.com/1dlife](https://jonmillen.com/1dlife/index.html)), Nachbarschaft `YYXYY`, Evolution-Ansicht (jede Gen. eine Zeile), Wrap-Ring, Seed **28–35 %**, Status `POP` / `SEED` / `GEN`, Neustart nach **20** Gen.

---

## PC — `pc/2d_game_of_life.py`

Python 3.8+, `curses` (unter Windows: `pip install windows-curses`).

```bash
python3 pc/2d_game_of_life.py
```

Editor, Musterbibliothek, Regelwerke (B/S), Torus, Zellalter, Statistik. Wichtige Tasten: Leertaste Pause, `.`/`N` Schritt, `P` Muster, `O` Regeln, `Q`/ESC Ende — Hilfe mit `H`/`?`.

---

## Commodore / MEGA65 (BASIC)

### C64

- 2D: [`c64/2d_game_of_life.bas`](c64/2d_game_of_life.bas) — 40×23, POKE Screen/`55296`, **extrem langsam**
- 1D: [`c64/1d_game_of_life.bas`](c64/1d_game_of_life.bas) — Evolution-Ansicht
- **VICE:** `x64`, laden, `RUN`

### C16 / Plus/4

- 2D/1D unter [`c16/`](c16/) — TED `3072`/`2048`, Boot-Lila (`COLOR 1,15,6`)
- **VICE:** `xplus4` oder C16, laden, `RUN`

### C128 — VIC-II 40 Spalten

- [`c128/2d_game_of_life_vic2-40.bas`](c128/2d_game_of_life_vic2-40.bas) — **extrem langsam**
- [`c128/1d_game_of_life_vic2-40.bas`](c128/1d_game_of_life_vic2-40.bas)
- Nur 40-Spalten-VIC; **`SLOW`** (nicht `FAST` — sonst schwarzer VIC-Screen)

### C128 — VDC 80 Spalten

- [`c128/2d_game_of_life_vdc-80.bas`](c128/2d_game_of_life_vdc-80.bas) — **extrem langsam**
- [`c128/1d_game_of_life_vdc-80.bas`](c128/1d_game_of_life_vdc-80.bas)
- FAST; VICE: zuerst **80col / VDC-Fenster**

### MEGA65

- 2D: [`mega65/2d_game_of_life_80.bas`](mega65/2d_game_of_life_80.bas) — **funktioniert auf Hardware**; `SPEED`, `T@&`
- 1D: [`mega65/1d_game_of_life_80.bas`](mega65/1d_game_of_life_80.bas)
- Disk: [`mega65/2d_game_of_life.d81`](mega65/2d_game_of_life.d81) / [`mega65/2d_game_of_life_80.prg`](mega65/2d_game_of_life_80.prg)

---

## Lizenz

Keine Lizenzdatei im Repository — bei Weitergabe bitte eine passende Lizenz ergänzen oder mit dem Maintainer klären.
