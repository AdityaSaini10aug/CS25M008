# Research Overview

## 1. Project Title

**OSINT-Based Risk Scoring of Ethereum Wallets: Integrating On-Chain Blockchain Data with Off-Chain Open-Source Intelligence**

## 2. Background and Motivation

Ethereum records transactions and smart-contract interactions on a public blockchain. On-chain analysis can reveal transaction histories, interaction patterns, and relationships between wallet addresses.

However, blockchain activity alone may not provide all the contextual information needed to assess the potential risk associated with a wallet.

Open-Source Intelligence (OSINT) refers to information collected and analysed from publicly accessible sources. Relevant off-chain information may provide additional context about wallet addresses or entities associated with blockchain activity.

This research investigates whether combining on-chain information with relevant off-chain OSINT can improve the information available for Ethereum wallet risk assessment.

## 3. Problem Statement

An assessment based solely on on-chain data may lack contextual information available from relevant public sources outside the blockchain.

The research problem is to investigate how on-chain blockchain features and off-chain OSINT can be integrated into an Ethereum wallet risk-scoring approach, and to evaluate whether the combined approach provides benefits over an appropriate on-chain baseline.

## 4. Research Objectives

1. Review existing research on blockchain wallet risk assessment and OSINT.
2. Study and implement the selected baseline algorithm.
3. Identify relevant on-chain features and potential off-chain intelligence sources.
4. Develop a documented method for integrating the two information sources.
5. Evaluate the approach using suitable datasets and metrics.
6. Compare the combined approach with appropriate baselines.
7. Document experimental findings, limitations, and reproducibility details.

## 5. Research Questions

- RQ1: What information can on-chain analysis provide for Ethereum wallet risk assessment?
- RQ2: What relevant contextual information can be obtained from publicly accessible off-chain sources?
- RQ3: How can on-chain features and off-chain OSINT be combined in a risk-scoring workflow?
- RQ4: How does the combined approach compare with an on-chain-only baseline under the same evaluation conditions?
- RQ5: What limitations affect the reliability, coverage, and reproducibility of the combined approach?

These questions may be refined as the literature review and experiments progress.

## 6. Planned Methodology

1. Literature review and selection of a baseline method.
2. Baseline algorithm implementation and verification.
3. Identification and preparation of relevant on-chain data.
4. Identification of suitable public OSINT sources.
5. Feature extraction and integration.
6. Experimental evaluation using documented configurations.
7. Comparison with baseline results.
8. Analysis of findings, limitations, and future work.

The final implementation details will depend on the selected algorithm, available data, and experimental requirements.

## 7. Evaluation Plan

The evaluation metrics will depend on the task and the available ground-truth labels.

Where appropriate, classification metrics may include precision, recall, F1-score, and confusion-matrix analysis. If the algorithm produces continuous risk scores rather than class predictions, suitable ranking or score-based evaluation methods may also be required.

Baseline and combined approaches should be compared using consistent datasets, splits, and evaluation procedures wherever feasible.

No experimental performance claims are made in this document. Results will be recorded after experiments have been conducted and verified.

## 8. Scope and Considerations

- Focus on Ethereum wallet risk assessment.
- Use relevant blockchain data and publicly accessible off-chain information.
- Document source provenance, collection dates, and feature derivation.
- Distinguish observed evidence from inferred risk.
- Record data limitations, potential false positives, and uncertainty.
- Follow applicable source terms, privacy requirements, and research ethics.

## 9. Current Status

**Status:** Research and experimental implementation in progress.

The baseline method, data sources, integration approach, and evaluation procedure will be documented as they are finalized.

## 10. Document Maintenance

This document will be updated as the research problem, methodology, and experimental design become more specific.

