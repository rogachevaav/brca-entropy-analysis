# Data description

The project uses annotated GenBank records for four BRCA-associated genes
in three mammalian species.

## Included genes

- BRCA1
- BRCA2
- PALB2
- BARD1

## Included species

- Homo sapiens
- Pan troglodytes
- Mus musculus

## Selected transcript models

| Gene | Homo sapiens | Pan troglodytes | Mus musculus |
|---|---|---|---|
| BRCA1 | NM_007294.3 | NM_001045493.1 | NM_009764.3 |
| BRCA2 | NM_000059.3 | XM_016925134.4 | NM_001081001.2 |
| PALB2 | NM_024675.3 | XM_063796860.1 | NM_001081238.2 |
| BARD1 | NM_000465.4 | XM_526019.7 | NM_007525.3 |

## File naming

- `hs` — Homo sapiens
- `pt` — Pan troglodytes
- `mm` — Mus musculus

Example:

`hs_BRCA1_gb.gb` — annotated BRCA1 genomic region for Homo sapiens.

## Source

The records were obtained from public NCBI GenBank / RefSeq annotations.

## Processing rules

One representative transcript was selected for each gene and species.
RefSeq NM_ transcripts were prioritized when available. Exons were extracted
from the selected mRNA model, and introns were defined as intervals between
consecutive exons.

Sequences that did not satisfy the entropy method's minimum length
requirements were excluded from the final statistical comparison.
