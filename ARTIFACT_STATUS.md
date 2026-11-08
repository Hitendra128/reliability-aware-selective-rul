# Artifact status and scientific reporting hierarchy

These statements describe the supplied `New folder.zip` only. They do not establish that the notebook code reruns successfully on another machine.

| Dataset | Frozen outcome and evidence | Reproduction limit |
|---|---|---|
| FD001 | Capped RUL 125, threshold 0.95, 37/100 accepted; full MAE 10.32247262, accepted MAE 8.18384464, gain 2.13862798; final 20,000-bootstrap CI roughly [-0.175565, 4.498796] | Two FD001 model checkpoints present; historical threshold/corruption and older bootstrap files also exist and must not override final analyses |
| FD002 | Capped RUL 125, threshold 0.8003345892330226, 211/259 accepted; full MAE 10.618375, accepted MAE 9.140482, gain 1.477893; 293/315 positive controlled-corruption scenarios | No FD002 `.pt` checkpoint in supplied ZIP; corruptions are selection-conditioned DEV evidence |
| FD003 | Raw RUL, threshold 0.76616064141995, 82/100 accepted; full MAE 27.2758997, accepted MAE 27.3115463, gain -0.0356466 | Negative held-out outcome must be retained; authoritative endpoint-level records and model checkpoint unavailable |
| FD004 | Raw RUL, DEV threshold 0.7873400997304446; 11 of 248 TEST engines too short for frozen 30-cycle window | TEST inference, risk and scoring were not admissible; never publish an invented or reconstructed TEST score |

## Source priority

1. **Publication-strengthening frozen reporting:** `results/cross_dataset_synthesis/manuscript_ready/publication_strengthening_631mf/` with its `FINAL_PUBLICATION_STRENGTHENING_MANIFEST_631MF.json` and listed checksums.
2. **Manuscript-ready cross-dataset summaries:** `results/cross_dataset_synthesis/manuscript_ready/`.
3. **Dataset-specific closure records:** such as `evidence/fd001_final/fd001_final_evidence.json` and FD004 admissibility contract JSONs; interpret according to their historical stages.
4. **Exploratory/intermediate notebooks and result folders:** preserved for provenance, not automatic authority for final reported numbers.

**Example of supersession:** `evidence/fd001_final/fd001_final_evidence.json` contains an earlier 10,000-bootstrap CI; final publication-strengthening results use a later 20,000-bootstrap analysis. Do not silently mix these values.

## Integrity check

The previous archive review verified that the 15 entries in the final publication-strengthening manifest matched their recorded SHA-256 checksums. Future releases should rerun checksum verification after copying/organizing files.

## Claim boundaries

- Controlled corruptions are imposed experimental sensor degradations, not observed naturally occurring failure modes.
- FD002's development selection and its degradation diagnostics share evidence; they cannot be called independent external confirmation.
- FD003's held-out negative result and FD004's unscored status are material outcomes.
- The original NASA files are absent and their exact historical local archive provenance is unresolved.
- Checkpoint and endpoint-level artifact gaps limit exact independent reruns.
