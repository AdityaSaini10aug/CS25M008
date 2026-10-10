# RiskProp Supervised Algorithm Notes

## Source
- Repository: https://github.com/lindan113/RiskProp
- Inspected upstream commit: ecfae2cae98a4420c1e643818cac33ba9b3e4301
- Source file: Supervised_Riskprop.py

## Inputs
- Transaction_Information.csv
- Account_Information.csv
- all_hash_0_hop_643_labels.csv

## Initialization
- Transaction confidence: 0.5
- Account trust: 0.5
- Account reliability: supervised_reliable_0 from account data

## Propagation equations
Trust:
T(v) = sum of incoming transaction score*confidence
       divided by in_degree(v).
If in_degree(v) is zero, trust is set to 0.5.

Reliability:
R(u) = sum of outgoing transaction confidence
       divided by out_degree(u).
If out_degree(u) is zero, the initial reliability is retained.

Confidence:
C(u,v) = [R(u) + (1 - abs(s(u,v) - T(v)))] / 2

Updated values are clipped to [0,1].

## Supervised reliability-update rules
- If node_label[node] == 1, skip the reliability update.
- If node < 643 and discription[node] == 'mining',
  skip the reliability update.
- Other accounts undergo the reliability update.
- Skipped accounts retain their initialized reliability during
  this update step, but still participate in trust and confidence
  propagation.

## Stopping condition
- Maximum iterations: 400.
- Stop when total absolute changes in trust, reliability,
  and confidence are all strictly less than 0.01.
- The code checks for NaN in the change accumulators.

## Risk score
Risk(u) = 10 - 10*R(u)

## Implementation observations
- The construction of supervised_reliable_0 is not shown
  in this script and must be investigated.
- The meanings of label values must be verified from the dataset.
- Account and description indices must be checked for alignment.
- The node < 643 condition is hard-coded.
- The transaction output header declares score before confidence,
  but the write statement outputs confidence before score.
- The results directory must exist before output files are opened.
- The confidence output file is not explicitly closed.

## Reproduction status
- Supervised source inspected.
- Original algorithm not yet executed.
- Required original dataset files are still missing.
- No reproduction results have been generated.
