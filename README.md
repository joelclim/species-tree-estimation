# Species Tree Estimation based on Compressed Mitochondrial Genome Sequences

**An alignment-free approach to phylogenetic inference using genomic data compression and information-theoretic similarity measures.**

## Overview

Phylogenetic tree estimation is fundamental to understanding evolutionary relationships among organisms. Conventional approaches typically rely on multiple sequence alignment (MSA), which can become computationally expensive when analyzing large genomic datasets.

This research investigates an alternative approach to phylogenetic inference by leveraging data compression algorithms to estimate similarities between mitochondrial genome sequences without requiring sequence alignment.

The study evaluates whether general-purpose and genomics-specific compression algorithms can recover evolutionary relationships among 19 vertebrate species.

The research builds upon the information-theoretic approach described by Bennett, Li, and Ma (2003), examining the feasibility of reproducing phylogenetic relationships using readily available compression tools.

## Research Objectives

1. Investigate the feasibility of alignment-free phylogenetic inference using compressed mitochondrial genome sequences.
2. Evaluate the compression efficiency and performance of general-purpose and genomics-specific compression algorithms.
3. Construct phylogenetic trees using pairwise sequence similarity measures derived from compressed file sizes.
4. Compare compression-based phylogenetic trees against an MSA-based consensus tree to assess their topological agreement.

## Methodology

The study analyzes complete mitochondrial genome sequences from **19 vertebrate species**, representing primates, ferungulates, rodents, marsupials, and galliformes.

The computational workflow consists of five major stages:

1. **Sequence acquisition:** Retrieve mitochondrial genome sequences from NCBI in FASTA format.
2. **Sequence preparation:** Generate pairwise concatenated genomic sequences for similarity analysis.
3. **Data compression:** Compress individual and paired sequences using gzip, bzip3, and Genozip.
4. **Phylogenetic reconstruction:** Calculate compression-derived pairwise similarity measures, construct distance matrices, and infer phylogenetic trees.
5. **Comparative evaluation:** Benchmark compression-based phylogenetic trees against an MSA-based reference using tree topology statistics.

The reference consensus tree was generated from an MSA-based analysis incorporating neighbor-joining, UPGMA, and maximum-likelihood phylogenetic reconstruction methods.

## Technologies and Tools

| Category | Tools |
|---|---|
| Programming and analysis | Python, Biopython, Pandas |
| Computing environment | JupyterLab, Conda |
| Sequence data | NCBI, FASTA |
| Compression algorithms | gzip, bzip2, bzip3, Genozip |
| Phylogenetic inference | ClustalW, FastTree |
| Tree analysis | DendroPy |
| Tree visualization | FigTree |

## Key Findings

The study found that compression-based methods can recover meaningful taxonomic groupings, although the inferred phylogenetic relationships do not fully reproduce the MSA-based reference tree.

Among the evaluated compression methods, Genozip generated the phylogenetic tree with the closest topological agreement to the reference.

### Robinson–Foulds Distance

| Compression Algorithm | RF Distance |
|---|---:|
| gzip (fast) | 33 |
| bzip3 | 25 |
| **Genozip** | **23** |

Lower Robinson–Foulds distances indicate greater topological agreement with the reference tree.

Genozip produced the lowest RF distance, followed by bzip3, while gzip demonstrated substantially weaker agreement.

These findings suggest that compression characteristics can influence the effectiveness of alignment-free phylogenetic reconstruction.

## Limitations and Future Research

The study was limited to a relatively small set of mitochondrial genome sequences and primarily evaluated differences in phylogenetic tree topology rather than evolutionary branch lengths.

Further research could investigate:

- Larger and more diverse genomic datasets.
- Alternative genomic compression algorithms and similarity measures.
- The relationship between compression efficiency and phylogenetic accuracy.
- Comparisons with other alignment-free methods, including k-mer-based approaches.
- Computational scalability and performance across different genome sizes.

## Research Significance

This project demonstrates how concepts from **information theory, data compression, and algorithm analysis** can be applied to biological sequence analysis.

It explores the intersection of computer science and evolutionary biology, providing a computational perspective on phylogenetic inference and the broader potential of alignment-free genomic analysis.
