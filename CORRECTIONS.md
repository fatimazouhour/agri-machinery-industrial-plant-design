# Corrections

After submission, the workbook and report were re-checked against the project brief. This file lists every change, so the original and corrected versions can be compared.

## A. Formula fixes in the workbook

Applied in `workbook/Flail_Mower_Plant_Calculations_CORRECTED.xlsx`. Everything else is unchanged; the original file is kept alongside.

| # | Cell | Before → After | Why | Effect |
|---|---|---|---|---|
| 1 | `$_BOM_CYCLE!L10` | `=K8/U28` → `=L9/U28` | The stamped-guard L = 1500 quantity skipped the bending scrap step. The L = 1750 row already did it correctly. | Stamped guards 9,777 → **9,977** / month |
| 2 | `$_WARE_BUFFER!J6` | `=$_BOM_CYCLE!K32` → `=$_BOM_CYCLE!K11` | The 1500×2000 sheet demand for L = 1500 pointed at the L = 1750 cell. | 63 → **79** LU of stock |
| 3 | `$_WARE_BUFFER!J7` | (empty) → `=$_BOM_CYCLE!K15` | The 1000×1500 sheet demand for L = 1500 was missing. | 40 → **75** LU of stock |
| 4 | `$_WARE_BUFFER!Q9:Q16` | `$_DATA!$Q$34` → each family's own cell (Q36, Q38, Q40, Q42) | Every item used the 3-day safety stock of metal sheets. Gears and hammer shafts have 1 day (brief, Table 10b). | Gear turnover 4.9 → **8.8**; hammer shafts 4.0 → **6.3** |
| 5 | `WORKERS_SAFETY!H32:H34`, `N10:N12` | 2 → 1 | The frequency multiplier FM can never exceed 1. The frequency-independent RWL uses FM = 1. | FILI 0.59 → **1.19** (guard L = 1750); SLI 1.06 → **1.37** |
| 6 | `SERVICE AREA…!B21` | `=22*4` (88) → `=2*4+2*4` (16) | Assembly operators = lines × stations. The flail mower needs 2 lines × 4 stations (`$_MANUF_PARTS_BATCH`, `OP_ASSEMBLING`). The rotary tiller is assumed to need the same 2 × 4, based on its demand of about 10,500 per month and the same 2-min cycle; **confirm with Team A**. | Total staff 330 → **156** |

These fixes flow on into the ABC analysis, EPEI buffers, warehouse areas and forklift count. The forklift total is still 4 for the flail-mower routes. Altogether 243 cells change value.

## B. Errors in the submitted report

The PDF is kept as submitted; these are corrections to its text:

- **§2.1:** 7,352 / 3,151 / 9,389 / 6,260 are **monthly** quantities, not daily.
- **§4.5:** the receiving paragraph mixes in the shipping numbers. The correct values are: receiving 918 LU/day, 27 trucks/day, **3 docks**, 93 m²; shipping 1,730 LU/day, 82 trucks/day, **5 docks**, 261 m².
- **§4.7:** "22 assembling stations" and 172 total staff. Corrected: 16 assembly operators per shift, **156** total.
- **§5 (NIOSH):**
  - The text refers to welding and assembly and "welded frames". The analysed task is the bending/stamping station (guards and hitch brackets).
  - The VLI table shown is Team A's, with five lowering heights.
  - "Adding another operator achieves LI < 1" does not hold for the 14 kg guard (FILI = 1.19).
- **§3.4:** the workstation descriptions mention "the motor". The flail mower has no motor; those tasks fit gearbox and covers.
- **Figure 4:** the L = 1750 BOM tree shows 3 reinforcement brackets. The brief and the workbook use **5**.

## C. Open points (not changed)

- **Shipping** is sized for 1,730 LU/day, while the plant produces about 1,190 finished machines per day (711 flail mowers + about 477 tillers, 1 machine per LU). The shipping-frequency assumption behind 1,730 should be checked.
- **The AutoCAD layout** (`drawings/Plant_Layout_v6.pdf`) was drawn with the original warehouse sizes and staffing. It has not been redrawn.
