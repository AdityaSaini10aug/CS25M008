# RiskProp Replication Log

## 2026-10-10 — Initial upstream inspection

### Environment
- macOS 26.6.2
- Apple Silicon (arm64)
- RAM: 16 GB
- System Python: 3.14.7
- Git: 2.55.0
- uv: installed
- Homebrew: installed

### Upstream source
- Repository: https://github.com/lindan113/RiskProp
- Branch inspected: main
- Local inspection clone: /tmp/riskprop-inspect/RiskProp

### Findings
- Original scripts require NumPy and pandas.
- README specifies Python 3.7, NumPy 1.21.2, pandas 1.3.5.
- Unsupervised script requires Transaction_Information.csv
  and Account_Information.csv.
- Supervised script additionally requires
  all_hash_0_hop_643_labels.csv.
- Current clone contains only all_hash_0_hop_803_labels.csv
  and data/readme.md in its data directory.
- Git history inspection found no tracked paths matching
  Transaction_Information.csv or Account_Information.csv.
- Git LFS is not installed locally.
- Original algorithm has not yet been executed.

### Status
BLOCKED: Required upstream dataset files are missing.

### Next actions
1. Check for an official supplementary dataset or author response.
2. Obtain the missing files from an authoritative source.
3. Verify dataset schema and record checksums.
4. Configure a compatible Python environment.
5. Run the original implementation.
6. Compare outputs with the paper.

### Reproducibility caution
Do not claim exact replication until the required dataset,
preprocessing, and evaluation protocol have been verified.

## Upstream source version

- Repository: https://github.com/lindan113/RiskProp
- Inspected commit: `ecfae2cae98a4420c1e643818cac33ba9b3e4301`

## 2026-10-10 — Dataset access request

### Action taken
- Sent an email to the RiskProp paper's first author requesting access
  to the original dataset files.

### Files requested
- Transaction_Information.csv
- Account_Information.csv
- all_hash_0_hop_643_labels.csv

### Status
WAITING: Author response pending.

### Next actions
1. Inspect the original implementation while waiting.
2. Verify the dataset files and their schemas if received.
3. Record the data source and checksums.
4. Run the experiments only after the required inputs are available.

## 2026-10-10 — Dataset obtained and algorithm execution

### Dataset
- Obtained the RiskProp dataset files from the dataset share:
  https://1drv.ms/u/s!AjeNZgmClbKY6kAJtpRCOg0_M39D?e=XsVy8m
- Dataset directory is stored outside the Git repository.
- Files used:
  - Account_Information.csv
  - Transaction_Information.csv
  - all_hash_0_hop_643_labels.csv
- Account records: 1,191,641
- Transaction records: 4,136,464
- Labelled accounts: 643
  - Label 0: 446
  - Label 1: 197
- Account indices are unique and consecutive from 0 to 1,191,640.
- Transaction IDs are unique and consecutive from 0 to 4,136,463.
- The 643 label-file indices match account indices 0 through 642.
- All 643 labels agree with the account-level label column.
- Dataset address-to-account-index mapping has not been independently verified.

### Environment
- Python: 3.10.20, arm64, in a virtual environment outside the Git repository.
- NumPy: 1.21.2
- pandas: 1.3.5
- The upstream README specifies Python 3.7; the replication environment uses Python 3.10.20.

### Unsupervised RiskProp
- Script: code/Unsupervised_Riskprop.py
- Execution completed successfully.
- Convergence reported after 74 iterations.
- Account output:
  results/20220205-Account-trust-reliabl-risk-unsupervised-riskprop.csv
- Transaction output:
  results/20220205-Transaction-score-confidence-unsupervised-riskprop.csv
- Account output contains 1,191,641 records.
- Transaction output contains 4,136,464 records.
- No missing or non-finite values were found in the checked numeric output columns.
- Reliability range: approximately 0 to 1.
- Risk range: 0 to 10.
- Maximum absolute difference from risk = 10 - 10 * reliability:
  approximately 3.55e-15.

### Supervised RiskProp
- Script: code/Supervised_Riskprop.py
- Execution completed successfully.
- Convergence reported after 74 iterations.
- Account output:
  results/20220205-Account-trust-reliabl-risk-supervised-riskprop.csv
- Transaction output:
  results/20220205-Transaction-score-confidence-supervised-riskprop.csv
- Account output contains 1,191,641 records.
- Transaction output contains 4,136,464 records.
- No missing or non-finite values were found in the checked numeric output columns.
- Reliability range: 0 to 1.
- Risk range: 0 to 10.
- Maximum absolute difference from risk = 10 - 10 * reliability:
  approximately 3.55e-15.

### Supervised versus unsupervised comparison
- Mean reliability:
  - Unsupervised: 0.7529236383
  - Supervised: 0.7526737287
- Mean risk:
  - Unsupervised: 2.4707636167
  - Supervised: 2.4732627135
- Mean trust:
  - Unsupervised: 0.2332695791
  - Supervised: 0.2332243773
- Accounts with reliability differences greater than 1e-12: 91,752.
- Accounts with risk differences greater than 1e-12: 91,809.
- Accounts with trust differences greater than 1e-12: 31,948.
- These comparisons describe output differences; they do not establish superior classification performance.

### Implementation issue observed
- Both scripts write transaction output columns under the header
  "Transaction,score,confidence".
- The write statement outputs confidence before Tx_Score, so the
  score and confidence values appear reversed relative to the header.
- Original scripts and generated outputs have not been modified to
  correct this issue.

### Current status
- Both algorithms executed and their output shapes and numerical
  consistency checks passed.
- Classification metrics have not yet been calculated.
- Agreement with the paper's reported experimental metrics has not
  yet been established.
- The raw dataset and generated result CSVs remain outside Git tracking.

### Next actions
1. Verify the paper's evaluation protocol before computing classification metrics.
2. Investigate the transaction output column-order issue.
3. Record dataset checksums and provenance details.
4. Decide how to preserve or publish large result files without committing
   the raw dataset or large generated CSVs to the main Git repository.
