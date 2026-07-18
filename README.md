# Recovering the Indo-European Language Family Tree Without Cognates
### A Comparison of Lexicalized and Delexicalized Representations


## Overview
This project investigates whether lexicalized (content-based) or delexicalized 
(structure-based) language representations better recover known Indo-European 
language family relationships, in settings where cognate sets or aligned 
parallel corpora aren't available. Using Universal Dependencies (UD v2.15) 
treebank data for 21 Indo-European languages across four subfamilies 
(Germanic, Romance, Slavic, Indo-Aryan), we reconstruct phylogenetic trees 
using multiple feature representations and compare them against an 
established ground-truth tree.

## Methods
**Lexicalized representations** (word-form/content-based):
- Top-50 most frequent word frequencies
- Word length distribution + character trigram overlap (Jaccard distance)
- Word2Vec embeddings (with and without PCA dimensionality reduction)
- Unaligned FastText embeddings

**Delexicalized representations** (structure-based):
- POS tag and dependency relation frequency vectors
- POS tag and dependency relation transition probabilities
- Dependency distance and direction (mean signed/absolute distance to head)

**Tree construction:** UPGMA and Neighbor Joining (NJ), using Biopython

**Evaluation:** Robinson-Foulds (RF) distance to ground truth, closest/farthest 
language pair analysis, and within- vs. between-subfamily distance comparison

## Files
- `report/project report.pdf` — final paper (pdf format)
- `code/COMP550_FINAL_PROJECT_COMPLETE.ipynb` — full pipeline (data processing, 
  representation construction, tree building, evaluation)

## Key Findings
- Lexicalized and delexicalized methods performed at comparable levels overall. 
  The strongest lexicalized methods (character trigram overlap, PCA-Word2Vec) 
  and the strongest delexicalized method (POS tag transitions) achieved similar 
  RF similarity scores against ground truth.
- Feature vector size had limited impact — POS tag frequency vectors (17 dims) 
  outperformed dependency relation transitions (~1,600 dims), suggesting the 
  type of signal matters more than dimensionality.
- Simple baselines (word length, top-50 word frequency) performed worst, though 
  even these recovered partial subfamily structure.
- The character trigram method's apparent success was partly an artifact of 
  shared writing systems (Latin vs. Cyrillic) rather than true genealogical 
  signal.


## Authors
This project was completed as the final project for COMP 550 (Natural Language Processing), McGill University, Fall 2025.

- Raisa Chowdhury
- Jaya Bonelli
- Sepehr Radmannia

