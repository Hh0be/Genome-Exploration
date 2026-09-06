# Genome Exploration II: Phasianus colchicus Assembly Analysis

## Methods
- *Platform*: Galaxy (usegalaxy.org)
- *Input*: ASM414374v1 genomic FASTA (322.1 MB, 39,678 sequences)
- *Tools used*: 
  - gfastats (assembly statistics)
  - Sort/Filter (length-based filtering)
  - getorf (ORF prediction)

## Key Results
- *Assembly size*: 1.82 Gb (scaffolds), 1.87 Gb (contigs)
- *Contiguity*: N50 = 16.7 Mb, L50 = 27
- *GC content*: 41.21%
- *ORFs identified*: 327 (≥300 bp)

## Reproducibility
All analyses performed in Galaxy history: [Link to your history]
Datasets are numbered and parameter settings documented in tool outputs.

## Notes
- Filtering ≥10 kb retained 588 scaffolds (45% of genome)
- Longest ORF: 7,116 bp (potential protein-coding gene)
- Assembly quality suitable for comparative genomics
