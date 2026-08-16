# Mini Racecar PCB

A custom electronics board for a **2WD, IR-controlled racecar robot**, designed in **KiCad**.

---

## Overview

| | |
|---|---|
| **Form factor** | < 100 mm × 100 mm |
| **Fabrication** | 2-layer rigid FR-4, via Robotistan PCB Service |
| **Battery input** | 2S–6S LiPo (4.5 V – 40 V input range) |
| **Logic compatibility** | Any 5 V-based microcontroller |
| **Motor support** | Low-reduction 3–6 V TT motors, 150 mA (no load) – 1.5 A (stall) |

---

## Power & Drive Architecture

The board combines a **buck-style power stage** (inductor + Schottky + electrolytic caps) to step the LiPo input down for logic rails, and a **dual full H-bridge** built from discrete `IRF540N` MOSFETs (driven via `IR2104` half-bridge drivers) to independently control two DC motors for differential steering. IR receiver pins bring in the remote-control signal.

---

## Bill of Materials

### Power Stage

| Ref | Value | Notes |
|---|---|---|
| L1 | 33 µH | Radial inductor, Fastron 07HCP |
| D1 | 5 A / 100 V Schottky | Buck rectifier |
| Q — power switching | 8× IRF540N | TO-220, vertical |
| IC — gate drivers | 4× IR2104 | DIP-8, half-bridge driver |

### Capacitors

| Ref | Value | Package |
|---|---|---|
| C1 | 100 µF / 16 V | Electrolytic |
| C2 | 220 µF / 16 V | Electrolytic |
| C9 | 470 µF / 16 V | Electrolytic |
| C12 | 470 µF / 16 V | Electrolytic |
| C7, C13 | 1 µF | SMD 1206 |
| C8, C15 | 10 µF | SMD 1206 |
| C3, C4, C11, C14 | 0.47 µF | SMD 0805 |
| C5, C6, C10, C16 | 0.1 µF | SMD 0805 |

### Diodes

| Ref | Value | Package |
|---|---|---|
| D1 | 5 A / 100 V Schottky | — |
| D2, D3, D4, D5, D6, D10, D11, D12 | 1N4148 | THT DO-35, 7.62 mm |
| D7, D8, D9, D13 | MURS260 | SMD, SMB |

### MOSFETs & Gate Drive

| Ref | Part | Package |
|---|---|---|
| Q1–Q8 | IRF540N | TO-220-3, vertical |
| IR2104 ×4 | Half-bridge driver | DIP-8 |

### Resistors

| Ref | Value (Ω) | Package |
|---|---|---|
| R1, R2, R3, R4, R6, R7, R9, R10 | 10 | SMD 0805 |
| R5, R8 | 0.1 (current sense) | SMD 0805 |

### Connectors

| Ref | Type | Footprint |
|---|---|---|
| Load1, Load2, Input | 2-pin terminal block | MaiXu MX126-5.0-02P, 5.00 mm pitch |
| IR_pins | 3-pin header | 2.54 mm pin header, vertical |
| IR_pins1 | Custom | — |

---

## Tooling

Designed entirely in **KiCad**.


