# DriftCheck: A Protocol for Detecting Construct Drift in AI Hallucination Benchmarks

DriftCheck is a longitudinal screening and psychometric validation protocol for 
detecting construct drift in AI hallucination benchmarks — i.e., identifying when 
a benchmark's items stop measuring the phenomenon they were designed to measure 
as models evolve across generations, distinct from simple knowledge/data drift.

## What this repository contains

- `notebooks/driftcheck_phase0_to_7.ipynb` — full pipeline:
  - **Phase 0**: longitudinal screening (accuracy drift, ceiling detection) 
    across TruthfulQA, HaluEval, and RAGTruth
  - **Phase 1**: Rasch (1PL) item difficulty estimation + Differential Item 
    Functioning (DIF) analysis on drift-flagged items
  - **Phase 5–7**: cross-family validation (Qwen lineage) against the primary 
    Llama-family results
- `data/driftcheck_sampled_item_ids.json` — frozen benchmark item sample IDs, 
  for reproducibility
- `docs/benchmark_lifecycle_protocol.md` — the Stable → Monitor → Retire → 
  Refresh lifecycle framework

## Data and results archive

Full results (item reports, DIF tables, judgments, cross-family validation 
summaries) are archived on Zenodo with a DOI: [link to be added]

## Requirements

See `requirements.txt`. Requires a Hugging Face token with access to gated 
Llama and Qwen model checkpoints (set as `HF_TOKEN`).

## Reproducing the results

1. Set `HF_TOKEN` (Kaggle Secrets or environment variable)
2. Run Phase 0–1 cells sequentially (see in-notebook markdown for GPU/CPU 
   requirements and kernel-restart points between phases)
3. Run Phase 5–7 for cross-family validation

## Citation

If you use this protocol or data, please cite:
[citation to be added upon publication]

## License

MIT (code) — see `LICENSE`. Benchmark data used (TruthfulQA, HaluEval, 
RAGTruth) retains its original respective licenses.
