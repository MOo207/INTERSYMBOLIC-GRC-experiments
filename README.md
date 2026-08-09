# INTERSYMBOLIC-GRC — Experiments Replication Package

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21865334.svg)](https://doi.org/10.5281/zenodo.21865334)

Experiment code and results for:

> **INTERSYMBOLIC-GRC: An Intersymbolic AI Framework for Technical Asset Risk Assessment Under NFCRM-1:2025**
> Mohammed Ismail Alamawy, Islamic University of Madinah.

This repository contains the replication package (experiment scripts and raw result files) supporting the paper and thesis. It is the citable artifact for the experimental evaluation.

## Contents

| Directory | Description |
|-----------|-------------|
| `scripts/` | All experiment and analysis scripts (ablation studies, LLM pipeline runs, statistical tests, SHAP/XAI analysis, figure generation) |
| `results/` | Raw experiment outputs (JSON): unified ablation, NSL-KDD ablation, safety tables, LLM risk generation, GRC metrics, cross-dataset controls |
| `pipeline/` | Core pipeline package imported by the scripts (risk scoring, NFCRM mapping, feature extraction, inference) |
| `ontology/` | GRC ontology (Turtle) and SHACL shapes used for validation |
| `rules/` | Symbolic rule definitions |
| `data/processed/` | Cleaned datasets used by the experiments (CIC-IDS2018 subset, NSL-KDD) |
| `data/external/` | Enrichment sources: CISA KEV snapshot, NVD enrichment, MITRE ATT&CK (enterprise), CMDB assets, NFCRM clause mapping |
| `data/raw/NSL-KDD/` | NSL-KDD train/test files (KDDTrain+, KDDTest+) |
| `requirements.txt` | Python dependencies |
| `REPRODUCIBILITY.md` | Notes on reproducing the experiments |

> **Note on CIC-IDS2018 raw data:** the raw CSE-CIC-IDS2018 dataset (~8 GB) is not included; download from the [official source](https://www.unb.ca/cic/datasets/ids-2018.html). The processed subset used in all experiments (`data/processed/cleaned_dataset.csv`) is included, so every reported number can be verified without the raw download. The NFCRM-1:2025 framework document is available from the [NCA regulatory documents page](https://nca.gov.sa/en/regulatory-documents/).

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

See [CITATION.cff](CITATION.cff).

- Version DOI (v1.0.0): [10.5281/zenodo.21865334](https://doi.org/10.5281/zenodo.21865334)
- Concept DOI (all versions): [10.5281/zenodo.21865333](https://doi.org/10.5281/zenodo.21865333)
