# ASTRO 2026 DVH constraints for MIM 7.4.5

This repository contains 42 scenario-specific CSV constraint sets derived from all 25 tables in the [ASTRO Dose-Volume Histogram Compendium, Appendix E3](https://www.astro.org/ASTRO/media/ASTRO/Patient%20Care%20and%20Research/PDFs/DVH_Compendium_AppendixE3_Tables_2.pdf). The 42 CSV files are in the repository root. The original ASTRO PDF and patient-specific records are not included.

## Use in MIM

1. Select the CSV matching the disease site, prescription, fractionation, and clinical branch. Letter suffixes distinguish branches such as left/right breast, liver function, one/two lungs, and bowel bag/loops. Do not apply every scenario to one plan.
2. In MIM 7.4.5, use Settings > General Preferences > Dose Constraints > Import CSV.
3. Confirm every contour against the actual RTSTRUCT. ASTRO_MAP_* is an intentional placeholder requiring case-specific mapping; it is not an evaluated contour.
4. Verify prescription dose, relative-dose interpretation, structure definitions and exclusions, laterality, and target coverage.
5. Compare representative MIM DVH values with the treatment planning system and obtain qualified clinical review before clinical use.

## Encoding and verification

The 42 CSVs contain 634 constraint rows: 587 primary-goal instances and 47 separately encoded secondary-goal instances. Another 222 secondary goals are encoded as positive warning margins. Strict source inequalities (< or >) and normalization goals without a comparator use MIM Report Value, with the exact source threshold retained in the English constraint name. They require manual interpretation. There are 136 ASTRO_MAP_* scenario-row instances and 76 Report Value instances.

Source-to-CSV verification passed for all 42 files and 388 unique Appendix E3 rows. An independent PDF text check found all 388 audited primary metric/goal pairs and all 196 nonblank secondary fields on their stated pages. All 42 files and 634 rows round-tripped through a locally installed MIM 7.3.7 CSV parser. That parser check does not establish successful import of every scenario in the MIM 7.4.5 graphical interface or patient-specific clinical validity.

## Source exceptions

- Table 3, row 11 has conflicting printed Secondary and Deviation directions for V90%. The secondary row is Report Value and is labeled as a source inconsistency.
- Table 21, row 8 prints Femoral Head V40 Gy 0% without a comparator. MIM rejects a V-function target volume of 0%. The CSV uses Maximum Dose as a Report Value surrogate; review the original V40 Gy text manually.

These are source-specific single-course planning goals, not patient-specific treatment decisions or cumulative reirradiation limits. This repository is an independent conversion and is not an ASTRO or MIM release.

Source: Puckett et al., Dose-Volume Histogram Compendium of Dose Constraints for Treatment Planning (ASTRO, 2026), Appendix E3. Source PDF SHA-256: 434C76BBC7DCE31702BE175482CDDBB22B02BC9CAB1ADCE099629CAB8184F17C.
