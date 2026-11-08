# Reliability-Aware Selective RUL Prediction under Controlled Sensor Degradation

**Curated research-evidence and partial-code archive for NASA C-MAPSS FD001–FD004.**

This repository preserves Jupyter notebooks and experimental artifacts associated with dataset-specific reliability-aware selective remaining useful life (RUL) prediction. The core workflow uses a GRU predictor, Monte Carlo dropout uncertainty, an empirical reliability-risk calibration and a frozen per-engine accept/abstain policy. Controlled sensor corruptions are used in development-stage diagnostics.

## Scope and reporting boundaries

- **FD001:** final frozen risk threshold `0.95`; 37 of 100 held-out engines accepted. Primary target is RUL capped at 125 cycles. Positive MAE-gain point estimate; the final bootstrap 95% CI spans zero.
- **FD002:** final frozen threshold `0.8003345892330226`; 211 of 259 engines accepted. Primary target is RUL capped at 125 cycles. Positive held-out selective gain. The 315 controlled-corruption scenarios are selection-conditioned development evidence, not independent held-out tests.
- **FD003:** raw, uncapped RUL target; 82 of 100 accepted; held-out selective MAE gain is slightly negative. This negative result is retained. The original authoritative endpoint-level arrays are not preserved in this archive.
- **FD004:** raw, uncapped RUL target. Frozen 30-cycle terminal-window admission rule prevented valid held-out inference/scoring because 11 of 248 TEST engines had fewer than 30 cycles. FD004 has **no valid held-out TEST score**; no new padding or post-hoc modification is permitted.

Do not compare capped-target and raw-target absolute MAEs as if they share the same target convention.

## Preserved contents

This repository has 8 Jupyter notebooks (`00_environment_check.ipynb` through `07_fd002_replication.ipynb`), selected result CSVs and JSON records, and two FD001 `.pt` checkpoints. Large `.npz` files are NOT in this curated repository and remain only in the original private backup. The later `07_fd002_replication.ipynb` notebook also includes work on FD003 and FD004; its name does not describe its full scope.

Key frozen reporting evidence is located under:

`results/cross_dataset_synthesis/manuscript_ready/publication_strengthening_631mf/`

The final reporting manifest in that directory records checksums for publication-strengthening artifacts, including the frozen threshold-attainable curves, fixed-policy bootstrap, and random-rejection summaries. Older files elsewhere in the archive are historical research records and must **not automatically be treated as the final authoritative analyses**.

## Data provenance

The underlying NASA C-MAPSS FD001–FD004 dataset is not bundled in this archive. Obtain it from its authorized public NASA distribution and retain a record of the exact data distribution and files used. The exact historical local dataset archive version could not be verified from the preserved evidence; do not claim that a newly downloaded copy is byte-identical without checking.

## Reproduction status

This archive is an **evidence and partial-code archive**, not a guaranteed one-command reproduction package. Some notebooks have historical absolute Windows paths; complete environment versions are not preserved; and FD002–FD004 trained-model checkpoints are not included. FD003 endpoint arrays cannot be reconstructed as if they were historically frozen. See `ARTIFACT_STATUS.md`, `REPRODUCIBILITY.md` and `RELEASE_CHECKLIST.md` for details.

The archived notebook execution outputs were generated in the original working environment. **Do not claim the current package has been rerun successfully in a clean environment.**

## Locating the frozen reporting results

Start with `results/cross_dataset_synthesis/manuscript_ready/`. For final uncertainty and selective-prediction reporting, consult `results/cross_dataset_synthesis/manuscript_ready/publication_strengthening_631mf/FINAL_PUBLICATION_STRENGTHENING_MANIFEST_631MF.json`, `publication_strengthening_summary_631mf.csv`, and the final threshold-attainable CSVs. For FD002 controlled-degradation selection-conditioned development evidence, consult `evidence/step6_reliability_signals/fd002_c4/`; for FD004 structural admissibility consult `evidence/fd004_test_structural_admissibility_630w10ar3_v2_safe.json`.

The repository is intentionally a **partial-code and evidence archive**. It does not establish a verified rerun of the historical model training or all downstream evaluations. See `REPRODUCIBILITY.md` for known blockers.

## Historical environment evidence

The original `00_environment_check.ipynb` saved output (retained in the untouched source archive, not the stripped review notebook) records:

- Python 3.10.11
- NumPy 2.2.6
- Pandas 2.3.3
- scikit-learn 1.7.2

Versions of other dependencies are not verified by that record. See `requirements-DRAFT.txt`.

## Suggested citation and reuse

The author has added an MIT `LICENSE` for author-owned original research code, subject to confirmation that every included code component is owned by the author or compatible with that license. NASA C-MAPSS source data and third-party software retain their respective rights; the MIT license must not be interpreted as relicensing them. A citable release and archival DOI should be created only after the release contents and privacy review are verified. Supporting Information and the manuscript provide additional methodological details and limitations.


## Archive composition and remaining release checks
This repository is a **curated subset** of the original 137 MB research ZIP, initially assembled for review. Its evidence-and-partial-code role is the intended public disclosure, **not** verified end-to-end reproduction. Before publication, the author must complete the manual source/privacy and license-scope review, confirm `LICENSE` is committed, and approve the repository state. Keep the original full ZIP unchanged and private.

- `notebooks/` contains **8 notebooks with identical cell source but saved cell outputs and execution counts removed** to keep the package reviewable. Historical absolute Windows paths remain in code; the notebooks have **not been executed** in a fresh environment. Original notebook outputs remain in the original ZIP.
- `results/` preserves the manuscript-ready cross-dataset files (including the frozen publication-strengthening manifest and tabular results) byte for byte.
- `evidence/` retains selected FD001, FD002, FD003 and FD004 records. Some records are **historical / superseded** and are not controlling for final reporting. Large NPZ arrays and many intermediate results remain only in the original archive.
- `models/` contains the two original FD001 checkpoints, which are historical binary artifacts and have not been loaded or validated here.
- `PACKAGE_INVENTORY.csv` provides source-path and SHA-256 hashes of every included file; `MANIFEST_VERIFICATION.md` summarizes validation.

**Before publishing:** manually inspect notebook sources and JSON/CSV for information that should not be public, confirm license scope, and retain the partial-reproduction caveat unless an independent clean execution test has actually succeeded. Do not claim the notebooks reproduce every figure or result.

## Release transparency

A static scan of the curated text files and notebooks found no standard email, private-key, AWS access-key or GitHub-token patterns. This is **not** a substitute for the author’s manual privacy and intellectual-property review. The checkpoints were not deserialized and no notebook was run. Historical local Windows project paths are retained for provenance and require adjustment for any future execution.
