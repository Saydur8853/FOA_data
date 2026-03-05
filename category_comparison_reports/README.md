# Category Comparison Reports

This folder stores comparison outputs between:
- source master file: `FOA Single Items.xlsx`
- category single file: `FOA Singles/<Category>-Single.xlsx`

## Generated files
- `mattress_title_changes_old_vs_mattress_single.csv`: title changes for the Mattress category, matched by SKU.

## CSV columns
- `category`: compared category name.
- `old_title`: title in `FOA Single Items.xlsx`.
- `new_title`: title in `FOA Singles/<Category>-Single.xlsx`.
- `changed_sku_count`: number of SKUs with that title mapping change.
- `skus`: SKU list affected by that mapping.

## How to run this for any other category (future)
1. Pick the category name exactly as it appears in the `Category` column in `FOA Single Items.xlsx`.
2. Open the corresponding file in `FOA Singles`, for example:
   - `Bedroom` -> `FOA Singles/Bedroom-Single.xlsx`
   - `Dining` -> `FOA Singles/Dining-Single.xlsx`
3. Compare rows by `SKU` (not by title text), because titles can be normalized/edited.
4. Check coverage first:
   - all source-category SKUs should exist in the category single file.
5. Then detect title changes:
   - for each matching SKU, compare source `Title` vs single-file `Title`.
6. Group output by `(old_title, new_title)` and include SKU count plus SKU list.
7. Save as a CSV in this folder named:
   - `<category>_title_changes_old_vs_<category>_single.csv`

## Notes
- A different unique-title count does not always mean missing products; title edits can merge/normalize names.
- SKU-level matching is the reliable check for product coverage.

Generated on: 2026-03-05 10:57:11
