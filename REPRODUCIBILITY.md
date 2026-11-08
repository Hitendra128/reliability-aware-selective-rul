# Reproducibility and execution status

**Status: PARTIAL.** This is a curated research-evidence archive, not a tested end-to-end executable reproduction. No notebooks or checkpoints were executed or loaded during review. The preserved CSV and JSON records can be inspected without rerunning training; those records do **not** substitute for original model training artifacts.

## 1. What is available

- Eight chronological research notebooks under `notebooks/`. Saved outputs and execution counts were removed from this review copy; original notebook outputs remain in the author's untouched `New folder.zip` backup. The later notebooks combine several stages and dataset experiments, and may depend on variables from historical interactive sessions.
- Frozen reporting artifacts under `results/cross_dataset_synthesis/manuscript_ready/`, especially `publication_strengthening_631mf/` with its frozen manifest.
- Selected supporting records under `evidence/`, including FD002 development-stage corruption diagnostics and FD004 TEST admissibility evidence.
- Two FD001 `.pt` model checkpoint files under `models/`. Their loadability has **not** been tested in a clean environment.

## 2. Data access and setup limitations

The original NASA C-MAPSS FD001–FD004 text files are **not** included. Obtain the dataset separately from an authorized public NASA source. The exact historical local archive/provenance of the data files was not recovered, so a fresh download should not be represented as byte-identical to the historical data.

Several notebook cells refer to `C:\RUL_Reliability_Research\...` (notably `06_reliability_signals_fd001.ipynb` and `07_fd002_replication.ipynb`). Those absolute paths require local adjustment. Changing a path for exploratory execution does **not** change the frozen historical experimental result; reruns must be independently labeled as new executions.

## 3. Software environment

Historical environment output retained in the original source archive identified Python 3.10.11, NumPy 2.2.6, pandas 2.3.3 and scikit-learn 1.7.2. Other package versions are **not verified**. `requirements-DRAFT.txt` is a discovery list, not a pinned, tested reproduction environment. GPU/CUDA settings and additional platform requirements were not validated.

Do not assert that running `pip install -r requirements-DRAFT.txt` reproduces the historical environment or that running notebooks in order recreates published results. A clean-environment test is still required before any execution claim.

## 4. Verification and scientific boundaries

- FD001 primary result uses capped RUL 125, final frozen risk threshold 0.95 and 37/100 held-out accepted engines. Older FD001 files may describe superseded policies or uncertainty intervals.
- FD002 primary result uses capped RUL 125, threshold 0.8003345892330226 and 211/259 held-out accepted engines. Controlled corruption is **selection-conditioned DEV evidence**. The FD002 final model checkpoint is not included.
- FD003 has an authentic negative held-out selective MAE gain. Original authoritative endpoint-level arrays and model checkpoint were not recovered. Do not invent or reconstruct them as originally frozen.
- FD004 TEST results were not validly scored because 11 of 248 trajectories failed the frozen 30-cycle minimum. Preserve its **unscored** status.
- FD003/FD004 use raw, uncapped targets; cross-dataset absolute MAEs must not be compared as though all targets used the same cap.

## 5. Before a public release

1. Keep the full original archive as an untouched private backup; it is not interchangeable with this curated subset.
2. Audit notebook source and binary artifacts for personal details, credentials and licensing issues. Automated pattern checks alone are not sufficient.
3. Decide whether to correct hard-coded paths in **separately identified execution copies** or to document that archived notebooks are historical and not portable. Do not silently alter the frozen evidence.
4. Test a clean environment **if** public documentation will claim runnable code; otherwise retain the limited-reproducibility statement.
5. Choose and add an appropriate license, then create a public release and citation/DOI only after the release review.
6. Update the manuscript Data Availability Statement only with a verified publicly accessible release or DOI. A private GitHub repository is not yet publicly available.
