# FD001–FD004 Final Results Reporting Bundle

## Table 1. Target-aware held-out results

| Dataset | Target | Role | Endpoints | Coverage | Full MAE | Accepted MAE | Abstained MAE | Selective gain | Relative reduction | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| FD001 | Capped RUL | primary | 100 | 37.0% | 10.322 | 8.184 | 11.578 | 2.139 | 20.72% | Scored |
| FD001 | Raw / uncapped RUL | secondary target sensitivity | 100 | 37.0% | 11.392 | 9.022 | 12.785 | 2.371 | 20.81% | Scored |
| FD002 | Capped RUL | final held-out authority | 259 | 81.5% | 10.618 | 9.140 | 17.115 | 1.478 | 13.92% | Scored |
| FD003 | Raw / uncapped RUL | final held-out authority | 100 | 82.0% | 27.276 | 27.312 | 27.114 | -0.036 | -0.13% | Scored |
| FD004 | Raw / uncapped RUL | primary held-out protocol | 248 | — | — | — | — | — | — | Not scored — structural protocol guard |

**Table note.** Absolute MAE values are dataset-specific and must not be interpreted as a cross-dataset ranking. Capped and raw/uncapped target results are shown explicitly.

## Table 2. FD004 supporting DEV and controlled-degradation evidence

| Evidence block | Measure | Value |
| --- | --- | --- |
| Clean DEV | Coverage | 80.0% |
| Clean DEV | Full MAE | 28.664 |
| Clean DEV | Accepted MAE | 27.116 |
| Clean DEV | Abstained MAE | 34.859 |
| Clean DEV | Selective MAE gain | 1.549 |
| Clean DEV | Relative MAE reduction | 5.40% |
| Controlled corruption | Executable scenarios | 381 |
| Controlled corruption | Positive / zero / negative | 365 / 0 / 16 |
| Controlled corruption | Positive-gain rate | 95.8% |
| Controlled corruption | Negative-gain family | stuck |
| Controlled corruption | Negative gain by severity | {"high": 11, "low": 1, "medium": 4} |
| Held-out TEST | Status | NOT_SCORED_UNDER_FROZEN_PROTOCOL_DUE_TO_SHORT_TEST_TRAJECTORIES |

**Table note.** FD004 DEV and controlled-corruption outcomes are supporting evidence only and are not held-out TEST results.

## Results

Reliability-aware selective prediction showed useful error separation in FD001 and FD002 and strong DEV/corruption evidence in FD004, but it did not generalize uniformly: FD003 produced a scored held-out negative result, and FD004 exposed a structural evaluation limitation of the fixed-window protocol.

### FD001

Selective filtering improved held-out TEST MAE under both the primary capped target and the retained raw-RUL secondary analysis, at relatively low realized coverage.

### FD002

The frozen reliability policy improved held-out TEST MAE for the piecewise-capped RUL evaluation.

### FD003

The frozen reliability policy did not improve held-out TEST MAE under the uncapped/raw RUL target; accepted MAE was slightly worse than full-population MAE.

### FD004

No held-out TEST performance estimate is reported under the frozen protocol because short TEST trajectories made the complete endpoint population structurally inadmissible for the fixed 30-cycle input rule.

Before TEST access, FD004 CLEAN DEV showed positive selective MAE gain. Across 381 executable controlled-degradation scenarios, 365 showed positive selective gain; all 16 negative cases were in the stuck-sensor family, concentrated most strongly at high severity.

## Discussion

The evidence supports reliability-aware selective RUL prediction as a useful error-separation mechanism in some settings, but not as a universally improving policy. FD001 and FD002 produced positive held-out selective gains, whereas FD003 produced a genuine held-out negative result.

FD004 strengthens the reliability argument at DEV stage and under controlled sensor degradation: most executable corruption scenarios retained positive selective gain. However, stuck-sensor corruption exposed the principal observed degradation failure mode.

FD004 also demonstrates that reliability evaluation depends on the admissibility of the underlying prediction protocol. The fixed 30-cycle input rule could not represent the full held-out endpoint population because 11 TEST trajectories were shorter than 30 cycles, so the frozen protocol required stopping before inference.

## Limitations

- Capped-target rows and raw/uncapped-target rows must remain explicitly distinguished. FD002 has no recovered raw-RUL final held-out authority, and FD004 has no scored held-out TEST MAE.
- Do not rank datasets by absolute MAE. C-MAPSS subsets differ in operating conditions, fault structure, target conventions, and evaluation circumstances. Absolute MAEs are reported as dataset-specific outcomes, not as a pooled performance ranking.
- FD004 CLEAN DEV and corruption results are supporting evidence only and must not be presented as held-out TEST performance.
- No genuine pre-existing FD002 raw-RUL final held-out authority was recovered. FD002 therefore contributes only its frozen piecewise-capped held-out result.
- FD003 is an important negative generalization result: the frozen policy slightly worsened accepted-set held-out MAE relative to the full TEST population.
- The current fixed-length model protocol has no prospectively frozen mechanism for TEST histories shorter than 30 cycles. Padding, engine exclusion, row repetition, or variable-length inference were not introduced after TEST access.
- All 16 negative selective-gain controlled-corruption scenarios in FD004 occurred in the stuck-sensor family, with failures concentrated most strongly at high severity.

## Claims that must not be made

- Do not claim that the selective policy improves every C-MAPSS subset.
- Do not rank datasets by absolute MAE.
- Do not treat capped and raw/uncapped target results as interchangeable.
- Do not report an FD004 held-out TEST MAE.
- Do not present FD004 DEV or corruption outcomes as held-out TEST outcomes.
- Do not create a new FD002 raw-RUL score from stored endpoint predictions.
- Do not retrofit padding or variable-length inference into the frozen FD004 primary TEST result.

## Recommended table notes

- FD001 reports both its primary capped-RUL evaluation and its retained raw-RUL secondary analysis.
- FD002 held-out results use the frozen piecewise-capped RUL target.
- FD003 uses uncapped TRAIN-derived RUL and produced a negative held-out selective-MAE result.
- FD004 held-out TEST was not scored because the frozen 30-cycle protocol was structurally incompatible with 11 of 248 TEST trajectories.
- FD004 DEV/corruption results are reported separately as supporting evidence and are not substitutes for held-out TEST performance.