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
