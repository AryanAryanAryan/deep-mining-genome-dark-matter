# Deep Mining the Genome's Dark Matter

> **Note:** The source code for this project is private. It was built as a COMP3900 capstone project at UNSW Sydney (Term 3, 2025), and the repository is owned by UNSW. This page explains what the project does and what I worked on.

## What the project does

Most of the human genome doesn't code for proteins, and much of it is still poorly understood. Our six-person team used DNA language models (GPN and GPN-MSA) to find highly conserved long non-coding RNA (lncRNA) regions on human chromosome 1. The goal was to give researchers a ranked list of promising regions and visual tools to explore what the models learned.

## How it works

1. **Prepare the data:** clean and line up gene annotations (GENCODE), the human reference genome (GRCh38) and conservation scores (phastCons).
2. **Train the models:** fine-tune GPN and GPN-MSA to tell highly conserved regions apart from weakly conserved ones.
3. **Find candidates:** score windows across the whole chromosome and merge high-scoring stretches into candidate regions, checked with ROC and precision-recall curves.
4. **Explore the results:** UMAP plots of the models' learned representations, plus an interactive web front end.

## What I worked on

- **UMAP pipeline:** built Python workflows that pull high-dimensional embeddings out of the GPN and GPN-MSA models and reduce them to 2D with UMAP, so researchers can see how the models group different DNA sequences.
- **Background research:** researched non-coding RNA and the modelling approaches the project was based on.
- **Presentation:** presented the project and its findings.

## Tech used

Python, PyTorch, HuggingFace Transformers, UMAP, NumPy, pandas, scikit-learn, UNSW's Katana high-performance computing cluster, JavaScript (front end), Docker

## References

- Benegas et al. (2023), *DNA language models are powerful predictors of genome-wide variant effects*, PNAS (GPN)
- Benegas et al. (2025), *A DNA language model based on multispecies alignment predicts the effects of genome-wide variants*, Nature Biotechnology (GPN-MSA)
