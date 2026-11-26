# Manuscript tables

Reserved results are from the structurally audited same-dataset snapshot; historical split integrity and historical nonaccess were not established. No external validation or test-based selection.

## Table 1. BCN20000 study partitions

| Partition | Images | Leakage groups |
| --- | --- | --- |
| Development | 7,813 | 2,286 |
| Original validation (excluded) | 1,973 | 571 |
| Reserved test | 2,578 | 715 |
| Total | 12,364 | 3,572 |

*Note: Partition counts from Cell 111 V2. Development used five group-aware folds. Reserved results are from the structurally audited same-dataset snapshot; historical split integrity and historical nonaccess were not established. No external validation or test-based selection.*

## Table 2. Reserved-test class distribution

| Class | Images | Groups | Image share (%) |
| --- | --- | --- | --- |
| AK | 129 | 48 | 5.00 |
| BCC | 580 | 196 | 22.50 |
| BKL | 241 | 70 | 9.35 |
| DF | 29 | 8 | 1.12 |
| MEL | 632 | 105 | 24.52 |
| NV | 842 | 255 | 32.66 |
| SCC | 94 | 25 | 3.65 |
| VASC | 31 | 8 | 1.20 |

*Note: Image counts and group counts are different units; the reserved test has 2,578 images and 715 leakage groups.*

## Table 3. Controlled architectural comparison

| Arm | Architecture | Clinical inputs | GATv2 | Adaptive mechanism | Head parameters |
| --- | --- | --- | --- | --- | --- |
| H0 | Image-only | No | No | No | 126,856 |
| H1 | Non-graph multimodal | Yes | No | No | 195,665 |
| H2 | Non-adaptive GATv2 | Yes | Yes | No | 195,665 |
| H3 | Adaptive GATv2 (proposed) | Yes | Yes | Yes | 195,665 |
| H4 | Adaptive non-graph control | Yes | No | Yes | 195,665 |

*Note: All arms use the frozen 1,440-dimensional Swin-T feature representation and the same four-epoch final training budget. Counts are trainable head parameters, not full-backbone counts.*

## Table 4. Grouped five-fold out-of-fold development performance

| Arm | Accuracy (%) | Macro-F1 (%) | Balanced acc. (%) | Fold Macro-F1 mean (%) | Fold SD (pp) |
| --- | --- | --- | --- | --- | --- |
| H0 | 55.80 | 37.38 | 37.93 | 36.81 | 4.05 |
| H1 | 56.87 | 37.34 | 37.15 | 37.34 | 4.47 |
| H2 | 57.12 | 38.41 | 38.75 | 37.87 | 3.77 |
| H3 | 57.03 | 37.73 | 38.24 | 37.57 | 3.24 |
| H4 | 56.87 | 36.37 | 36.63 | 36.13 | 2.82 |

*Note: Pooled OOF metrics from 7,813 development images in 2,286 groups. Fold mean and sample SD are separate from pooled Macro-F1. Development results are not reserved-test results.*

## Table 5. Reserved-test performance under natural metadata availability

| Arm | Accuracy (%) | Macro-F1 (%) | Balanced acc. (%) | Macro ROC-AUC | MEL recall (%) | SCC recall (%) |
| --- | --- | --- | --- | --- | --- | --- |
| H0 | 58.81 | 40.59 | 41.98 | 0.8487 | 62.50 | 36.17 |
| H1 | 60.43 | 40.30 | 41.02 | 0.8568 | 64.87 | 36.17 |
| H2 | 61.09 | 40.07 | 40.81 | 0.8566 | 65.35 | 38.30 |
| H3 | 61.79 | 41.65 | 43.11 | 0.8593 | 68.99 | 46.81 |
| H4 | 60.98 | 41.71 | 43.23 | 0.8579 | 68.99 | 42.55 |

*Note: Macro ROC-AUC is one-vs-rest on a 0–1 scale. H3 is the proposed arm, not a test-selected winner. Reserved results are from the structurally audited same-dataset snapshot; historical split integrity and historical nonaccess were not established. No external validation or test-based selection.*

## Table 6. Natural-condition performance with paired group-bootstrap uncertainty

| Arm | Accuracy (%) | 95% CI | Macro-F1 (%) | 95% CI |
| --- | --- | --- | --- | --- |
| H0 | 58.81 | [55.50, 62.02] | 40.59 | [36.78, 44.68] |
| H1 | 60.43 | [57.08, 63.67] | 40.30 | [36.39, 44.32] |
| H2 | 61.09 | [57.80, 64.30] | 40.07 | [36.58, 43.64] |
| H3 | 61.79 | [58.47, 65.02] | 41.65 | [37.71, 45.75] |
| H4 | 60.98 | [57.68, 64.19] | 41.71 | [37.61, 45.93] |

*Note: Descriptive 95% percentile intervals, 10,000 saved class-stratified group-bootstrap draws. These are not the multiplicity-adjusted primary contrast intervals.*

## Table 7. Proposed H3: per-class reserved-test performance

| Class | Images | Precision (%) | Recall (%) | Specificity (%) | F1 (%) | ROC-AUC |
| --- | --- | --- | --- | --- | --- | --- |
| AK | 129 | 27.61 | 28.68 | 96.04 | 28.14 | 0.8591 |
| BCC | 580 | 69.08 | 62.41 | 91.89 | 65.58 | 0.9040 |
| BKL | 241 | 36.79 | 29.46 | 94.78 | 32.72 | 0.7764 |
| DF | 29 | 11.36 | 17.24 | 98.47 | 13.70 | 0.7893 |
| MEL | 632 | 70.66 | 68.99 | 90.70 | 69.82 | 0.8822 |
| NV | 842 | 72.59 | 75.18 | 86.23 | 73.86 | 0.9019 |
| SCC | 94 | 29.33 | 46.81 | 95.73 | 36.07 | 0.8814 |
| VASC | 31 | 11.36 | 16.13 | 98.47 | 13.33 | 0.8797 |

*Note: Sensitivity equals recall. AUC is one-vs-rest (0–1). Point estimates only; small class supports limit interpretation.*

## Table 8. Missing-metadata stress-test performance

| Arm | Natural F1 (%) | Worst F1 (%) | Worst drop (pp) | All-missing F1 (%) |
| --- | --- | --- | --- | --- |
| H1 | 40.30 | 37.77 | 2.52 | 37.83 |
| H2 | 40.07 | 37.32 | 2.76 | 37.32 |
| H3 | 41.65 | 39.24 | 2.41 | 39.24 |
| H4 | 41.71 | 39.62 | 2.09 | 40.29 |

*Note: Worst is the minimum over natural plus seven forced-removal scenarios (M00–M07). Smaller degradation is better; larger absolute F1 is better. H0 is image-only and does not require metadata stress testing.*

## Table 9. Predeclared primary contrasts with Bonferroni-adjusted confidence intervals

| Contrast | Endpoint | Difference (pp) | 98.33% CI (pp) | Positive lower bound |
| --- | --- | --- | --- | --- |
| H1-H0 | Natural Macro-F1 | -0.29 | [-3.19, +2.42] | No |
| H3-H2 | Worst-case Macro-F1 | +1.92 | [-0.48, +4.95] | No |
| H3-H4 | Worst-case Macro-F1 | -0.38 | [-1.59, +0.85] | No |

*Note: 10,000 paired class-stratified group-bootstrap draws. Worst-case endpoint recomputed within each draw. None of the three primary superiority criteria was met; this does not establish equivalence.*

## Table 10. Exploratory image-occlusion faithfulness on development examples

| Intervention | Cases | Mean target-logit drop | Top > comparator (cases) |
| --- | --- | --- | --- |
| Top-ranked 4 tiles | 16 | 1.7371 | N/A |
| Fixed random 4 tiles | 16 | 0.6187 | 15 |
| Bottom-ranked 4 tiles | 16 | -0.2007 | 16 |

*Note: Sixteen class-stratified training examples, one per group. Positive drop means the original predicted-class logit decreased after deletion. This is not independent clinical explanation validation.*

## Table 11. Exploratory metadata-removal analysis on development examples

| Removed clinical information | Changed cases | Mean target-logit drop |
| --- | --- | --- |
| Age | 16 | 0.9721 |
| Sex | 16 | 0.8469 |
| Anatomical site | 16 | 1.0929 |
| All three fields | 16 | 2.4583 |

*Note: Means are over cases whose observation changed, not necessarily all 16 examples. Interventions are model perturbations, not causal clinical evidence.*

## Table 12. Clinical metadata availability in the reserved test

| Field | Observed images | Missing images | Observed (%) |
| --- | --- | --- | --- |
| Age | 2,558 | 20 | 99.22 |
| Sex | 2,558 | 20 | 99.22 |
| Anatomical site | 2,551 | 27 | 98.95 |

*Note: Observed counts are field-specific; overlapping missingness is possible. Availability at prospective clinical prediction time was not validated.*

## Table 13. Uncalibrated probability performance under natural metadata availability

| Arm | ECE (15 bins) | Multiclass Brier sum | Negative log-likelihood |
| --- | --- | --- | --- |
| H0 | 0.0773 | 0.5465 | 1.1514 |
| H1 | 0.1161 | 0.5375 | 1.1461 |
| H2 | 0.1113 | 0.5348 | 1.1435 |
| H3 | 0.1180 | 0.5411 | 1.1750 |
| H4 | 0.1244 | 0.5451 | 1.1791 |

*Note: Lower values are better. Point estimates from saved probabilities; no post-hoc calibration or threshold fitting.*
