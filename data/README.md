# The practice data

**These numbers are invented for practice.** They are not a real experiment.

`viability_plate.csv` is a 96-well plate-reader export from a made-up
viability assay. Two cell lines were treated with the degrader dTAG-13 for
72 hours, then cell viability was measured with CellTiter-Glo (light output
in relative light units, RLU).

- **parental** cells (rows A–D) have no tag.
- **FKBP12F36V-tagged** cells (rows E–H) carry a dTAG on an essential
  protein, so dTAG-13 should degrade it and the cells should die.

| Columns | Treatment |
|---|---|
| 1–2 | DMSO (vehicle control) |
| 3–10 | dTAG-13, 0.001 to 3 µM |
| 11 | staurosporine 1 µM (kills all cells) |
| 12 | medium only, no cells (background) |

The file is a real-looking export, which means it is not perfectly clean.
