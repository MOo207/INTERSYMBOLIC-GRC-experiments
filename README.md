# INTERSYMBOLIC-GRC — Experiments Replication Package

Experiment code and results for:

> **INTERSYMBOLIC-GRC: An Intersymbolic AI Framework for Technical Asset Risk Assessment Under NFCRM-1:2025**
> Mohammed Ismail Alamawy, Islamic University of Madinah.

This repository contains the replication package (experiment scripts and raw result files) supporting the paper and thesis. It is the citable artifact for the experimental evaluation.

## Contents

| Directory | Description |
|-----------|-------------|
| `scripts/` | All experiment and analysis scripts (ablation studies, LLM pipeline runs, statistical tests, SHAP/XAI analysis, figure generation) |
| `results/` | Raw experiment outputs (JSON): unified ablation, NSL-KDD ablation, safety tables, LLM risk generation, GRC metrics, cross-dataset controls |
| `requirements.txt` | Python dependencies |
| `REPRODUCIBILITY.md` | Notes on reproducing the experiments |

## Key experiments

- **Unified ablation (CIC-IDS2018, N=60/180)** — rule-based, Random Forest, XGBoost, pure-LLM, and tri-stage pipelines on an identical test set (`results/unified_ablation/`).
- **NSL-KDD ablation (N=50)** — cross-dataset generalization and under-escalation safety analysis (`results/nslkdd_ablation/`, `results/nslkdd_risk_ablation/`).
- **Permuted-CVE control** — CVE-identity ablation for the safety effect (`results/nslkdd_permuted_cve_control.json`).
- **LLM risk generation and control recommendation** — parse rate, SHACL conformance, hallucination audit (`results/llm_risk_generation.json`, `results/llm_control_recommendation.json`).
- **XAI analysis** — SHAP feature attribution and rule alignment (`results/shap_top20_features.json`, `results/confidence_gated_override.json`).

## LLM backend

All LLM experiments call Claude models (Haiku 4.5, Sonnet 4.6) through the Claude CLI subprocess wrapper in `scripts/claude_cli_client.py`. No API keys are stored in this repository.

## License

MIT — see [LICENSE](LICENSE).

## Citation

See [CITATION.cff](CITATION.cff). A Zenodo DOI badge will appear here after the first release is archived.
