# Public-release readiness checklist — evidence and partial-code archive

This repository is **not** a verified end-to-end reproduction package. All frozen experimental values remain unchanged. Check each item against the current GitHub commit before changing visibility.

## Already completed or provisionally confirmed

- [x] The author kept an untouched full research ZIP backup separate from GitHub (based on author confirmation).
- [x] The curated repository contains 8 notebooks, selected evidence, frozen reports, and FD001 checkpoints.
- [x] `README.md`, `ARTIFACT_STATUS.md`, `REPRODUCIBILITY.md` and the inventory/manifest documentation were prepared.
- [x] The author reports adding an MIT `LICENSE` to the private GitHub repository; **confirm the actual file and copyright holder before release**.
- [x] No `pyvenv.cfg` or original 137 MB ZIP was included in the curated review package.
- [x] An automated text scan found no common private-key, token, AWS key, or email patterns. This **does not certify** personal-data or credential safety.

## Must complete before making the repository public

- [ ] Confirm the corrected `README.md`, `ARTIFACT_STATUS.md`, and this checklist are committed and visible on GitHub.
- [ ] Manually inspect the notebooks, CSV/JSON records, and names/paths for sensitive content, third-party material, and license compatibility. Historical `C:\RUL_Reliability_Research` project paths are not portable.
- [ ] Verify that the actual GitHub `LICENSE` is MIT and that the author has the rights to license the original code. Do not relicense NASA's source data or third-party dependencies.
- [ ] Confirm README correctly says only *partial code and selected frozen evidence* are available. Notebooks and checkpoint loading have **not** passed an independent rerun test.
- [ ] Keep superseded FD001 results clearly subordinate to the final 0.95-threshold reporting manifest.
- [ ] Review GitHub's commit/file history before changing visibility: making a private repository public can expose its previous commits, not just the latest README.
- [ ] Approve the final public contents and only then change GitHub visibility from Private to Public.

## After public release

- [ ] Open the repository URL without signing into GitHub to confirm public access.
- [ ] Optionally create an immutable Zenodo archive/DOI after the release files are verified.
- [ ] Update the manuscript Data Availability Statement with the verified public URL/DOI and explicit partial-reproducibility limits.
- [ ] Keep the original full backup private and never claim unscored FD004 TEST results or newly reconstructed FD003 original endpoints.
