# Pre-release checklist — do not upload the original ZIP unchanged

- [ ] Keep an untouched offline backup of `New folder.zip` and the frozen manifests.
- [ ] Add `README.md`, `ARTIFACT_STATUS.md`, and a verified dependency manifest.
- [ ] Remove `pyvenv.cfg` from the public bundle: it records a local Windows installation path and is not a usable environment specification.
- [ ] Review Jupyter cell source, saved outputs and notebook metadata for personal names, local paths, tokens, credentials, or machine details. Retain scientifically necessary data and do not edit frozen numeric records.
- [ ] Identify older FD001 analyses and label them **historical / superseded** rather than deleting scientific provenance without documentation.
- [ ] Separate or clearly label final authoritative reports and exploratory notebooks.
- [ ] If independently saved FD002–FD004 checkpoints, original preprocessing transforms/configurations, and missing endpoint records actually exist, inventory and checksum them before deciding whether to include them. Do **not** regenerate them as 'original frozen' artifacts.
- [ ] Record the official NASA C-MAPSS download source, dataset acquisition instructions and provenance limits. Do not needlessly redistribute the source dataset.
- [ ] Test a clean environment on a separate machine if claiming notebooks are executable end-to-end. Otherwise keep the 'partial reproducibility' caveat.
- [ ] Choose a license intentionally. No software license is included in this starter because the author has not selected one.
- [ ] Decide where to host code versus larger binary evidence files; do not upload the entire 137 MB archive as one GitHub blob.
- [ ] Create an archived release/DOI only after a release has been verified.
- [ ] Update the manuscript Data Availability Statement with the actual verified repository URL/DOI, never a placeholder.
