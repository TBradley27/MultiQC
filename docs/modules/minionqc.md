---
name: minionqc
url: https://github.com/roblanf/minion_qc
description: >
  Quality control for long reads from ONT (Oxford Nanopore Technologies) sequencing.
---

The MinIONQC module parses results generated by [MinIONQC](https://github.com/roblanf/minion_qc).
It uses the `sequencing_summary.txt` files produced by ONT (Oxford Nanopore Technologies) long-read
base-callers to perform QC on the reads.
It allows quick-and-easy comparison of data from multiple flowcells

The MultiQC module parses data in the `summary.yaml` MinIONQC output files.
