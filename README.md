# CS25M008 — MTP Research Project

## Project Title

**OSINT-Based Risk Scoring of Ethereum Wallets: Integrating On-Chain Blockchain Data with Off-Chain Open-Source Intelligence**

## 1. Project Overview

This project investigates how on-chain blockchain information and off-chain Open-Source Intelligence (OSINT) can be combined to assess potential risk associated with Ethereum wallets.

On-chain analysis examines publicly recorded blockchain activity, including wallet transactions and interaction patterns. Off-chain OSINT involves gathering relevant information from publicly accessible sources outside the blockchain.

The project aims to investigate whether combining these two information sources can provide a more informative wallet risk assessment than relying on on-chain information alone.

## 2. Problem Statement

Traditional blockchain wallet analysis primarily relies on on-chain transaction data and interaction patterns. However, blockchain activity alone may not provide all the contextual information needed to understand a wallet's potential risk.

Publicly available off-chain information may provide additional context about wallet addresses, associated entities, and observable relationships.

This research investigates the integration of on-chain analysis and off-chain OSINT to develop and evaluate a more comprehensive Ethereum wallet risk-scoring approach.

## 3. Research Objectives

- Study existing approaches to blockchain wallet risk assessment.
- Understand and implement the selected baseline algorithm.
- Identify relevant on-chain features and publicly available off-chain intelligence.
- Investigate methods for integrating the two information sources.
- Conduct controlled experiments to evaluate the implemented approach.
- Compare experimental findings with baseline results and relevant published work.
- Document methodology, implementation decisions, limitations, and findings.

## 4. Research Methodology

The planned research workflow consists of the following stages:

1. **Literature review:** Study relevant research papers, algorithms, evaluation metrics, and research gaps.
2. **Baseline implementation:** Understand and implement the selected reference algorithm.
3. **On-chain analysis:** Identify relevant blockchain data and derive appropriate features.
4. **Off-chain OSINT collection:** Identify relevant public sources and document the collection methodology.
5. **Data integration:** Investigate how on-chain and off-chain features can be combined.
6. **Experimental evaluation:** Run experiments using documented datasets, configurations, and evaluation procedures.
7. **Comparative analysis:** Compare the proposed approach with suitable baselines using appropriate metrics.
8. **Documentation:** Record results, limitations, reproducibility details, and future improvements.

This workflow describes the planned methodology. The implementation and completion status of each stage will be documented as the research progresses.

## 5. Repository Structure

```text
CS25M008/
├── README.md
├── .gitignore
├── data/
├── docs/
├── experiments/
├── results/
└── scr/
```

- `data/` — Dataset descriptions, data sources, schemas, and preparation notes.
- `docs/` — Research paper index, literature review, methodology, meeting notes, and technical documentation.
- `experiments/` — Experiment configurations, execution instructions, and experiment logs.
- `results/` — Evaluation metrics, result tables, figures, and comparative analysis.
- `scr/` — Source code, if implementation files are maintained in this repository.

The separate `Papers/` directory in the parent `MTP/` workspace is reserved for the broader research and experimental work and is not automatically included in this repository.

## 6. Experimental Documentation

Each experiment should record:

- Experiment objective and hypothesis, where applicable.
- Dataset or input source and preprocessing steps.
- Algorithm or baseline version.
- Software environment and dependencies.
- Parameters and configuration.
- Command or procedure used to execute the experiment.
- Evaluation metrics and observed results.
- Comparison with relevant baseline or published findings.
- Limitations, observations, and reproducibility notes.

Reported results will distinguish between values published in reference papers and values obtained from our own experiments.

## 7. Reproducibility

The repository will document the software environment, dependencies, data sources, configuration settings, and execution instructions required to reproduce experiments wherever feasible.

Sensitive credentials, API keys, and other secrets must not be committed. Dataset handling and OSINT collection will follow applicable access restrictions, usage terms, and ethical considerations.

## 8. Current Project Status

**Status:** Research and experimental implementation in progress.

The repository is being organized to maintain research documentation, implementation notes, experiment records, and results in a version-controlled environment.

Specific implementation milestones and experimental findings will be added as they are completed and verified.

## 9. Research Integrity

This repository is intended to maintain a transparent record of the research process. Planned work, completed implementation, published findings, and independently reproduced results will be documented separately.

## 10. Maintainer

- **Roll Number:** CS25M008
- **GitHub:** [AdityaSaini10aug](https://github.com/AdityaSaini10aug)
