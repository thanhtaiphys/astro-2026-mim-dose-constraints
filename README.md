# ASTRO 2026 DVH constraints for MIM 7.4.5

This repository contains 42 scenario-specific CSV constraint sets derived from all 25 tables in the [ASTRO Dose-Volume Histogram Compendium, Appendix E3](https://www.astro.org/ASTRO/media/ASTRO/Patient%20Care%20and%20Research/PDFs/DVH_Compendium_AppendixE3_Tables_2.pdf). The 42 CSV files are in the repository root.

## Source documents

- [Original article PDF](Puckett_2026_ASTRO_DVH_Compendium.pdf) ([publisher record and DOI](https://doi.org/10.1016/j.prro.2025.11.003); Puckett et al., 2026; [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)).
- [Appendix E3: compilation of all 25 ASTRO tables](https://www.astro.org/ASTRO/media/ASTRO/Patient%20Care%20and%20Research/PDFs/DVH_Compendium_AppendixE3_Tables_2.pdf) (official ASTRO PDF).

## Use in MIM

1. Select the CSV matching the disease site, prescription, fractionation, and clinical branch. Letter suffixes distinguish branches such as left/right breast, liver function, one/two lungs, and bowel bag/loops. Do not apply every scenario to one plan.
2. In MIM 7.4.5, use Settings > General Preferences > Dose Constraints > Import CSV.
3. Confirm every contour against the actual RTSTRUCT. ASTRO_MAP_* is an intentional placeholder requiring case-specific mapping; it is not an evaluated contour.
4. Verify prescription dose, relative-dose interpretation, structure definitions and exclusions, laterality, and target coverage.
5. Compare representative MIM DVH values with the treatment planning system and obtain qualified clinical review before clinical use.



