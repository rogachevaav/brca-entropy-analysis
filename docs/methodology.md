# Methodology

## 1. Input data

The input consists of GenBank files containing genomic sequences and
structured biological annotations.

## 2. Representative transcript selection

For each gene and species:

1. mRNA features were matched with the corresponding CDS features.
2. Matching was performed using `transcript_id` when available.
3. RefSeq `NM_` transcripts were prioritized over predicted `XM_` models.
4. Candidates were then ranked by CDS length and mRNA length.
5. One transcript model was selected for further analysis.

## 3. Exon and intron extraction

Exon coordinates were obtained from the selected mRNA feature.

Introns were defined as intervals between consecutive exons of the same
transcript model.

For each region, the following attributes were stored:

- gene
- species
- region type
- region number
- start coordinate
- end coordinate
- sequence length
- nucleotide sequence

## 4. Entropy calculation

Two measures were calculated:

- Koslicki topological entropy
- Jin generalized topological entropy

The generalized entropy calculation used `k = 3`.

Sequences that did not satisfy the minimum length requirement were marked
as unsuitable for the final comparison.

## 5. Statistical analysis

For exon and intron groups, the following statistics were calculated:

- number of observations
- mean
- median
- standard deviation
- minimum
- maximum

Spearman rank correlation was used to evaluate the association between
sequence length and entropy.

## 6. Sliding-window profiles

Local entropy profiles were calculated using:

- window size: 1000 bp
- step size: 100 bp
- generalized entropy parameter: k = 3

Exon coordinates were added to each profile to compare local entropy
changes with gene structure.

## 7. Limitations

- Entropy estimates are affected by sequence length.
- Only a small number of sufficiently long exons remained after filtering.
- Exon and intron distributions partially overlap.
- Local entropy minima do not always coincide with exon boundaries.
- Entropy alone should not be interpreted as a diagnostic or functional
  marker.
