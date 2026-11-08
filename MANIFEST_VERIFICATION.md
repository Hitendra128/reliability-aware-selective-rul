# Manifest and package verification

- Source: user-supplied `New folder.zip`; source archive was only **read**, never overwritten.
- Every file retained in the `results/` and `evidence/` directory is byte-for-byte identical to its original archive member, as recorded in `PACKAGE_INVENTORY.csv`.
- The frozen `FINAL_PUBLICATION_STRENGTHENING_MANIFEST_631MF.json` lists 15 files; **all 15 SHA-256 hashes matched** the original ZIP contents during this packaging run.
- Notebook **cell sources were retained**, but output fields, execution counts and nonessential runtime metadata were removed. Their file hashes therefore differ from the original. This package is NOT a replacement for original notebook outputs.
- No notebook code, model checkpoints, or downloaded dataset were executed, deserialized or independently validated.
- This curated subset omits large NPZ arrays, most historical FD001 work and some intermediate results. The full uploaded original ZIP remains the evidence archive.
- This review draft has **not been checked for all possible personal information** in notebook source or binary files and must not be published unchanged.
