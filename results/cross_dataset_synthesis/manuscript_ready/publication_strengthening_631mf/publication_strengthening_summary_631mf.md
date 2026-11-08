# Publication-Strengthening Reporting Evidence — STEP 6.31M-F

## Governance

This bundle is reporting-only.

- Scientific recomputation: False
- Model inference / MC dropout: False
- Raw TEST access: False
- Raw RUL access: False
- Prediction regeneration: False
- Label reconstruction: False
- Threshold or policy selection: False
- Primary held-out results changed: False
- FD003 reconstructed: False
- FD004 reopened: False

The original STEP 6.31L empirical closure remains authoritative.

## FD001 — capped RUL primary target

Frozen TEST coverage: 0.370000

Full MAE: 10.322473

Accepted MAE: 8.183845

Frozen selective MAE gain: 2.138628

Matched-random fraction as good or better:
0.042850

Endpoint-bootstrap selective-gain 95% percentile interval:
[-0.175565,
 4.498796]

Fraction of endpoint-bootstrap replicates with positive selective gain:
0.965300

FD001 contains 13 unique risk values
across 100 endpoints.

Within-tie permutation normalized MAE-AURC:
- mean: 0.851533
- 2.5%: 0.805416
- 97.5%: 0.899928
- minimum sampled: 0.762113
- maximum sampled: 0.945566
- fraction below random-ranking reference 1.0:
  1.000000

Interpretation:
FD001 provides favorable and directionally stable evidence, but its
endpoint-bootstrap 95% interval includes zero. The direction of the AURC
advantage is robust to tied-risk ordering, while its exact magnitude is
tie-sensitive.

## FD002 — capped RUL

Frozen TEST coverage: 0.814672

Full MAE: 10.618375

Accepted MAE: 9.140482

Frozen selective MAE gain: 1.477893

Matched-random fraction as good or better:
0.000000

Endpoint-bootstrap selective-gain 95% percentile interval:
[0.788583,
 2.246237]

Fraction of endpoint-bootstrap replicates with positive selective gain:
1.000000

Within-tie permutation normalized MAE-AURC:
- mean: 0.868100
- 2.5%: 0.867933
- 97.5%: 0.868266
- minimum sampled: 0.867880
- maximum sampled: 0.868318

Interpretation:
FD002 provides strong and consistent evidence that the frozen reliability
ranking identifies a lower-error accepted subset. The result is robust to
matched random rejection, endpoint resampling, and tied-risk ordering.

## FD003

No new row-level analysis was performed.

Original frozen held-out result:
- coverage: 0.820000
- full MAE: 27.275900
- accepted MAE: 27.311546
- selective MAE gain: -0.035647

Interpretation:
The held-out negative result remains unchanged and is retained as an explicit
counterexample to universal selective-prediction improvement.

## FD004

No new held-out analysis was performed.

FD004 remains:
NOT_SCORED_UNDER_FROZEN_PROTOCOL_DUE_TO_SHORT_TEST_TRAJECTORIES

## Statistical boundary

Matched-random rejection is a reporting baseline at exactly matched frozen
coverage.

Endpoint bootstrap quantifies sampling variability conditional on the already
frozen trained model and policy.

It does not quantify retraining variability, random-seed variability, or
architecture-selection uncertainty.

No formal model-training significance claim is made.
