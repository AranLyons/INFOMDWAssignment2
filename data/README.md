# missForest paper datasets

Downloaded 16 October 2026. Seven publicly available datasets are stored in separate subfolders. Original archives and extracted source files are retained. No artificial missingness, scaling, filtering, or imputation has been applied.

## Files and verified dimensions

| Folder | Data file(s) | Verified raw contents | Preparation for the paper experiment |
|---|---|---|---|
| parkinsons | raw/parkinsons.data | 195 rows, 24 columns including name and status | Drop name and status to obtain 195 x 22 continuous measurements. Ignore the additional telemonitoring directory bundled by UCI: it is a different dataset. |
| musk | raw/clean1.data | 476 rows, 169 columns | Drop the first two identifier columns. Keep the last class column for the 476 x 167 mixed experiment; remove it for the 476 x 166 continuous experiment. Both compressed and decompressed data are included. |
| spect | raw/SPECT.train and raw/SPECT.test | Together 267 rows, 23 columns | Combine both files and exclude the first diagnosis column to obtain the paper's 22 binary features. Treat features as categorical. This is SPECT, not SPECTF. |
| promoter | raw/promoters.data | 106 rows, 3 fields: class, name, sequence | Remove the name and split the 57-character DNA sequence into categorical columns. The paper describes including the class as another variable; confirm the experimental column selection. |
| lymphography | raw/lymphography.data | 148 rows, 19 columns including class | Treat integer codes as categorical. Retain the class to match the paper's 19-column version. |
| isoprenoid | isoprenoid_original.txt | 39 gene rows, 118 numerical expression values per gene plus six annotation fields | Skip the introductory text, exclude annotations, and transpose expression values to obtain 118 x 39. Contrary to the article's general description of 40 genes, the actual supplementary file contains 39 gene rows, matching missForest's dimensions. |
| insulin | GDS3715.soft | 12,626 probe rows, 110 sample columns and two annotation columns | The expression table lies between !dataset_table_begin and !dataset_table_end. Exclude ID_REF and IDENTIFIER and transpose to 110 x 12,626. This matches the reported dimensions; identical preprocessing to the original missForest experiment has not been established. |

Dimensions were checked from the downloaded files. Original missing values, value types, and any additional transformations still need checking when preparing a reproduction. Matching dimensions alone does not prove that preprocessing is identical to the paper.

## Sources

- Parkinsons: https://archive.ics.uci.edu/dataset/174/parkinsons
- Musk Version 1: https://archive.ics.uci.edu/dataset/74/musk+version+1
- SPECT Heart: https://archive.ics.uci.edu/dataset/95/spect+heart
- Promoter Gene Sequences: https://archive.ics.uci.edu/dataset/67/molecular+biology+promoter+gene+sequences
- Lymphography: https://archive.ics.uci.edu/dataset/63/lymphography
- Isoprenoid: https://link.springer.com/article/10.1186/gb-2004-5-11-r92 (Additional data file 1)
- Insulin: https://www.ncbi.nlm.nih.gov/sites/GDSbrowser?acc=GDS3715 (associated series GSE22309)

Exact download URLs, archive sizes, and SHA-256 checksums are recorded in download_manifest.json. The five UCI archives include their original dataset documentation.

## Not downloaded

No verified public download was located for the exact Gaucher (40 x 590), GFOP (595 x 18), or Children's Hospital (55 x 124) benchmark matrices. No substitute data has been added. See the missForest paper's acknowledgements for the providers of GFOP and Children's Hospital, and Smit et al. (2007) for Gaucher.
