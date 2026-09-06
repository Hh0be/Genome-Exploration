# Genome Exploration II: Phasianus colchicus Assembly Analysis

## Objective

  This project aims to analyze the structural integrity and biological potential of the Phasianus colchicus genome assembly (ASM414374v1). By generating assembly statistics, performing length-based filtering, and predicting Open Reading Frames (ORFs), we seek to evaluate the assembly's contiguity, identify high-confidence genomic regions, and estimate the number of potential protein-coding genes. The findings will inform the assembly's quality and its utility for further genomic research.

## 1. Genome Identity & Source

*   **Species:**
*Phasianus colchicus* (Common Pheasant)
*   **NCBI Assembly Accession:** ASM414374v1
*   **Isolate:** SZU-A5-319
*   **Assembly Level:** Scaffold-level (Whole Genome Shotgun)
*   **Source File:** Phasianus_colchicus.genomic.fna.gz
*   **File Size:** 322.1 MB
*   **Total Sequences Uploaded:** 39,678
*   **Data Source:** NCBI GenBank / Galaxy Upload

---

## 2. Assembly Statistics (Original)

The initial assembly quality was assessed using gfastats. The genome exhibits high contiguity typical of modern avian assemblies, with a significant portion of the genome contained in chromosome-scale scaffolds.

| Metric | Value |
| :--- | :--- |
| *Total Scaffold Length* | 1,817,256,832 bp (~1.82 Gb) |
| *Total Contig Length* | 1,869,579,689 bp (~1.87 Gb) |
| *Number of Scaffolds* | 39,678 |
| *Number of Contigs* | 59,673 |
| *Scaffold N50* | 16,662,894 bp (~16.7 Mb) |
| *Scaffold L50* | 27 |
| *Contig N50* | 166,868 bp |
| *Contig L50* | 1,537 |
| *Largest Scaffold* | 42,839,634 bp (~42.8 Mb) |
| *Smallest Scaffold* | 291 bp |
| *GC Content* | 41.21% |
| *Total Gaps in Scaffolds* | 19,995 |
| *Total Gap Length* | 7,044,423 bp |

**Interpretation:**
  The Scaffold N50 of ~16.7 Mb indicates that half of the genome is contained within just the 27 largest scaffolds. This suggests a high-quality assembly where most chromosome arms are represented by single, contiguous sequences. The GC content of 41.21% is consistent with known avian genomes, which tend to be slightly GC-rich compared to mammalian genomes.

---

## 3. Sequence Length Structure

The five longest sequences in the assembly were identified to understand the chromosome-scale structure. These sequences likely correspond to the largest macro-chromosomes of P. colchicus.

| Rank | Sequence ID | Length (bp) |
| :--- | :--- | :--- |
| 1 | NW_022265245.1 | 42,839,634 |
| 2 | NW_022265349.1 | 39,946,719 |
| 3 | NW_022265324.1 | 32,499,962 |
| 4 | NW_022265451.1 | 29,444,388 |
| 5 | NW_022265362.1 | 27,985,125 |

**Observation:**
  There is a distinct separation between the top 5 sequences (all >27 Mb) and the remaining assembly. This "long tail" distribution is characteristic of high-quality de novo assemblies where the largest scaffolds successfully capture entire chromosomes, while the remainder consists of fragmented micro-chromosomes or unplaced regions.

---

## 4. Length-Filtering Experiment (≥10 kb)

To assess the impact of fragmentation, sequences shorter than 10,000 bp (10 kb) were removed. This simulates a "high-confidence" subset of the assembly.

### Comparison: Original vs. Filtered

| Metric | Original Assembly | Filtered (≥10 kb) | Change |
| :--- | :--- | :--- | :--- |
| *Total Scaffold Length* | 1,817,256,832 bp | 993,218,481 bp | *-45.4%* |
| *Number of Scaffolds* | 39,678 | 588 | *-98.5%* |
| *Scaffold N50* | 16,662,894 bp | 11,992,639 bp | *-28.0%* |
| *Scaffold L50* | 27 | 26 | *-3.7%* |
| *GC Content* | 41.21% | 48.96% | *+7.75%* |

**Key Findings:**
1.  **Massive Fragment Reduction:** 98.5% of the sequence count was removed, yet nearly half (45.4%) of the total genomic sequence was retained. This confirms that the vast majority of sequences in the original assembly are very short fragments.
2.  **GC Content Shift:** The GC content increased from 41.21% to 48.96% in the filtered set. This suggests that the removed short fragments were predominantly AT-rich. In avian genomes, short, AT-rich fragments often represent repetitive elements, telomeric regions, or low-coverage assembly artifacts.
3.  **Contiguity Preservation:** The L50 remained nearly identical (27 vs. 26), indicating that the largest, most important scaffolds were preserved despite the aggressive filtering.

---

## 5. ORF Exploration

**Target Sequence:** NW_022206055.1 (Unplaced genomic scaffold, scaffold947_cov42)  
**Tool Used:** getorf (EMBOSS)  
**Parameters:** Minimum ORF size = 300 bp

### Results Summary
*   *Total ORFs Identified:* 327
*   *Longest ORF:* 7,116 bp (Coordinates: [17901 - 25016])
*   *Shortest ORF (visible):* 303 bp
*   *Average ORF Length:* ~1,500 bp (estimated from sample)

### Sample ORF Data
| ORF ID | Coordinates | Length (bp) |
| :--- | :--- | :--- |
| _1 | [483 - 812] | 330 |
| _3 | [1223 - 2731] | 1,509 |
| _7 | [4113 - 7151] | 3,039 |
| _38 | [17971 - 24981] | 7,011 |
| _39 | [17901 - 25016] | *7,116* |

### ORF vs. Confirmed Gene
An *Open Reading Frame (ORF)* is a continuous stretch of codons that begins with a start codon (ATG) and ends with a stop codon. While ORFs are potential protein-coding regions, they are not confirmed genes.
*   *Why?* Many ORFs occur by chance in non-coding DNA.
*   *Confirmation:* To confirm a gene, we would need evidence of transcription (RNA-Seq), translation (Proteomics), or significant homology to known proteins in other species. The presence of very long ORFs (>7 kb) in this scaffold strongly suggests functional protein-coding genes, as random ORFs rarely exceed 1-2 kb.

---

## 6. Biological Interpretation

  The *Phasianus colchicus* genome assembly shows strong chromosome-scale contiguity, with a scaffold N50 of 16.7 Mb and five scaffolds over 27 Mb, indicating successful assembly of most chromosome arms. Its 41.21% GC content is consistent with typical avian genomes.

  Length filtering highlighted a trade-off between completeness and quality. Removing sequences under 10 kb eliminated 98.5% of fragments while retaining nearly half of the genomic content, resulting in a cleaner assembly but suggesting the original dataset contains many small, potentially unreliable fragments.
ORF analysis identified 327 potential protein-coding regions ranging from 300 bp to over 7 kb. The longest ORFs support genuine coding potential, although confirmation requires functional annotation or expression data.

  Overall, the assembly provides a strong resource for pheasant comparative genomics and evolutionary research, with further scaffolding and annotation likely to improve its value.


---

## 7. Reproducibility & Methods

*Galaxy History Link:*  
[https://usegalaxy.org/u/hh0be/h/genome-exploration-ii-palopalo](https://usegalaxy.org/u/hh0be/h/genome-exploration-ii-palopalo)

*Workflow Steps:*
1.  *Data Upload:* Uploaded Phasianus_colchicus.genomic.fna.gz to Galaxy.
2.  *Statistics:* Ran gfastats on the original FASTA to generate baseline metrics (Dataset #2).
3.  *Sorting:* Used Compute sequence length and Sort to identify the longest scaffolds (Dataset #4).
4.  *Filtering:* Used Filter sequences by length to retain sequences ≥10,000 bp (Dataset #5).
5.  *Filtered Stats:* Ran gfastats on the filtered dataset to compare metrics (Dataset #6).
6.  *ORF Finding:* Extracted sequence NW_022206055.1 and ran getorf (EMBOSS) with min length 300bp (Dataset #8).

*Software Versions:*
*   Galaxy Tool: gfastats (v1.3.1)
*   Galaxy Tool: getorf (EMBOSS v6.6.0.1)
*   Galaxy Tool: Filter sequences by length

---
