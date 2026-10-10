# RiskProp Unsupervised Algorithm Notes

## Source
- Repository: https://github.com/lindan113/RiskProp
- Inspected upstream commit: ecfae2cae98a4420c1e643818cac33ba9b3e4301
- Source file: Unsupervised_Riskprop.py

## Inputs
- Transaction_Information.csv
- Account_Information.csv

## Initialization
- Transaction confidence: 0.5
- Account trust: 0.5
- Account reliability: unsupervised_reliable_0 from account data

## Update equations

For transaction u -> v, let s(u,v) be its de-anonymization score
and c(u,v) its confidence.

Trust:
T(v) = sum over incoming transactions of s(u,v)*c(u,v)
       divided by in_degree(v).
If in_degree(v) is zero, trust is set to 0.5.

Reliability:
R(u) = sum over outgoing transactions of c(u,v)
       divided by out_degree(u).
If out_degree(u) is zero, the initial reliability is retained.

Confidence:
C(u,v) = [R(u) + (1 - abs(s(u,v) - T(v)))] / 2

The updated values are clipped to [0,1].

## Stopping condition
- Maximum iterations: 400
- Stop when total absolute changes in trust, reliability,
  and confidence are all strictly less than 0.01.
- The code checks for NaN in the change accumulators.

## Risk score
Risk(u) = 10 - 10*R(u)

## Implementation observations
- node_label, score, incount_for_node, and outcount_for_node
  are initialized or loaded but unused in the shown script.
- Convergence uses sums of absolute changes, not mean changes.
- The transaction output header declares score before confidence,
  but the write statement outputs confidence before transaction score.
- Account and transaction indexing assumptions need verification
  against the original CSV files.
- The results directory must exist before output files are opened.
- The confidence output file is not explicitly closed in the script.

## Reproduction status
- Source inspected.
- Original algorithm not yet executed.
- Required original dataset files are still missing.
- No reproduction results have been generated.
