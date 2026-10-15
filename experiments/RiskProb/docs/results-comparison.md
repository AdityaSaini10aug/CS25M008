# RiskProp Replication: Results Comparison

## 1. Objective

The objective of this experiment is to compare the results obtained by running the original RiskProp supervised and unsupervised algorithms on the datasets provided with the authors' implementation against the results reported in the RiskProp paper.

The original algorithm implementations and datasets were used without modification.

- **Original repository:** https://github.com/lindan113/RiskProp
- **Published paper:** https://ieeexplore.ieee.org/document/10713353/
- **Algorithms evaluated:** Unsupervised RiskProp and supervised RiskProp (RiskProp+).

## 2. Execution Summary

Both algorithms executed successfully and converged after 74 iterations.

| Item | Value |
|---|---:|
| Accounts | 1,191,641 |
| Transactions | 4,136,464 |
| Unsupervised algorithm | Completed |
| Supervised algorithm | Completed |
| Convergence iterations | 74 for each algorithm |

The results were generated using the authors' original scripts and supplied dataset files.

## 3. Results Comparison

| Metric | Paper: Unsupervised RiskProp | Our unsupervised result (803 labels) | Paper: RiskProp+ | Our supervised result (160 additional labels) |
|---|---:|---:|---:|---:|
| Precision | 71.48% | 71.48% | 70.91% | 70.91% |
| Recall | Requires verification | 81.48% | 84.78% | 84.78% |
| F1-score | 76.15% | 76.15% | 77.23% | 77.23% |
| Accuracy | 84.56% | 84.56% | 85.63% | 85.62% |
| AUC | 83.69% | Not yet compared on the same evaluation basis | 85.37% | 90.95% |

**Important:** The supervised comparison uses the 160 additional labelled accounts, whereas the unsupervised comparison uses all 803 labelled accounts. These are different evaluation populations, so this is an initial comparison rather than proof of an exact, like-for-like reproduction.

The unsupervised recall was calculated from the confusion matrix: 198 true positives out of 243 labelled illicit accounts, giving 81.48%. The paper's recall entry needs to be checked against the published table before a definitive comparison is claimed.

## 4. Interpretation

The unsupervised results reproduce the reported Precision, F1-score, and Accuracy values for the 803 labelled accounts.

For the 160 additional labelled accounts, the supervised results reproduce the reported Precision, Recall, and F1-score values, while Accuracy differs by approximately 0.01 percentage points due to rounding or calculation details.

The supervised AUC calculated on the 160-account subset is 90.95%, compared with the paper's reported 85.37%. This difference should not be interpreted as an improvement until the evaluation population, score orientation, and evaluation procedure are confirmed to be the same.

## 5. Conclusion

Running the original RiskProp implementation produced results that match several reported metrics closely. However, the current comparisons use different labelled-account populations for the two algorithms, and the AUC comparison has not yet been established on a common evaluation basis.

Therefore, the results provide encouraging evidence of replication, but a complete claim of exact reproduction requires verification of the paper's evaluation details and a like-for-like comparison.

## 6. Reproducibility Notes

- Original algorithm scripts were retained unchanged.
- Original dataset files were retained unchanged.
- Both algorithms completed successfully and converged after 74 iterations.
- Large raw datasets and generated output CSVs are not included in this report.
- This document records the current comparison; unresolved metric differences are explicitly identified rather than treated as confirmed matches.
