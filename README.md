# CohortCert: shared evidence and proof costs

[Current main paper](paper/CohortCert_ICDE2027_Final.pdf) · [Main LaTeX source](paper/CohortCert_LaTeX_Source.zip) · [Technical Companion](paper/CohortCert_Technical_Companion.pdf) · [Companion source](paper/CohortCert_Technical_Companion_Source.zip) · [Reading guide](READING_GUIDE.md) · [Authors](authors.csv)

**Zida Yang, Zisheng Kuang, Guquan You, Yongjun Dai, Junqin Chen, Haobing Liu, Jiexin Zheng, Cong Wang, Xiaolong Shi.**

The first four authors share first authorship. **Xiaolong Shi is the sole corresponding author** (xlshi@gzhu.edu.cn). Cong Wang is ordinary author eight. The current manuscript has 12 body pages and 14 total pages with 35 references. The Technical Companion is a separate online supplement, not an appendix to the submission PDF.

## What the system does

An analyst may ask several comparisons, equivalence judgments or a top-set question at once. CohortCert reads expensive labels incrementally, reuses them across overlapping cohorts and requested comparisons, and returns a complete request only when its count evidence supports every item. A separate offline evaluator bounds how few reads could supply the same kind of correct proof on realized paths. This is hindsight diagnosis, not information given to the online allocator.

## Current paper and fixed evidence

This v5 rewrite uses one numerical example, a notation table, plain-language formula bridges, three groups of completion constraints, a study map and explanatory results tables. Full definitions and frozen parameters remain in the companion. Numerical findings, method implementations, empirical inputs and all six supplied vector figures are unchanged; no new experiment is claimed.

Current main PDF SHA-256: `3d1ec83b7830b4358e8b4a1e0f41fd947237916d8b83be533eb04d05dd119e3a`.
Companion PDF SHA-256: `0d214adb6e71ee19ce9ab58879b550dfb8d6c3a67694558f102fa368a02ca523`.
[PAPER_ARTIFACT_BINDING.json](PAPER_ARTIFACT_BINDING.json) binds the manuscript, companion, sources, nine-author list and four original archives. [SHA256SUMS.txt](SHA256SUMS.txt) and [RELEASE_FILES_SHA256.json](RELEASE_FILES_SHA256.json) give file hashes.

The four evidence archives remain fixed at [`aae1e7b`](https://github.com/yzd2002/CohortCert/tree/aae1e7b071906d12c11f3eb230b9aee981f8adc1). The main paper links this repository and states that evidence pin; current manifests identify its manuscript/companion. The preceding manuscript is preserved at [`3f61dbc`](https://github.com/yzd2002/CohortCert/tree/3f61dbc5503f0f9457de82f68b7395e695e94b7a). Earlier repository history and access receipts retain their own recorded identities and scopes. Frozen component READMEs describe capture-time status; use the current outer binding for paper identity.

This is a Regular Research Paper supplement. It does not claim conference acceptance or EAB-complete reproduction. Author-specific COI/CMT declarations, submission administration and internal reviews are excluded from the public repository.

## Start here

Download and extract the four archives into the same parent directory. Their original internal directory names are retained so that archived provenance and manifests remain valid.

Download checksums are provided in `SHA256SUMS.txt`; on Linux, `sha256sum -c SHA256SUMS.txt` checks the release payload after all listed files have been downloaded.

| Download | Contents | Verification performed |
|---|---|---|
| [fast_analysis.zip](fast_analysis.zip) | Main-table and summary analysis, six scientific figures, seven-configuration MAST presentation, fixed public inputs and saved outputs | Analysis outputs checked against the manuscript; current MAST presentation executed and checked against the admitted audit |
| [method_sources.zip](method_sources.zip) | 542 original Python source files, method/control/audit entry points, 24 fixed CivilComments/GoEmotions CPU-study inputs including saved label maps and embeddings, and original study-A inputs | Source and fixed-input identities checked; methods were not rerun as part of packaging |
| [study_A_identity_addendum.zip](study_A_identity_addendum.zip) | Original study-A record identities and their provenance | Complements the base method archive without modifying its frozen manifest |
| [final_diagnostics.zip](final_diagnostics.zip) | Separate synthetic 205/197/171 construction, N=100 logical-interface enumeration, stdlib reproduction entry point, and supplemental runtime plot | Original finite evidence independently checked; final portable entry point executed without external dependencies |

The `study_A_identity_addendum.zip` archive resolves the **record-identity file** omission described in the historically frozen base-source README. Keep both archives: the base contains the original A labels/ranks; the addendum contains the matching record identities. This archival combination does not reset any historical execution permission or fill censored paths.

## Quick start: analysis and integrity

The analysis was checked in an existing Linux/Python 3.11 environment. Exact installed versions are listed in `submission_artifact_current_working_candidate_v2/requirements/requirements_analysis_tested.txt`. A fresh dependency installation and other operating systems have not been validated.

After extracting `fast_analysis.zip`:

```sh
cd submission_artifact_current_working_candidate_v2
python3 -B analysis_reproduce.py verify
```

This checks the packaged member hashes; it does not rerun statistical methods. To regenerate the current MAST table and heatmap from the closed public audit, first install the listed analysis dependencies in your chosen Python environment, then run:

```sh
env OPENBLAS_NUM_THREADS=1 OMP_NUM_THREADS=1 MKL_NUM_THREADS=1 NUMEXPR_NUM_THREADS=1 ARROW_IO_THREADS=1 python3 -B analysis_reproduce.py mast --out MAST/mast_audited_publication_outputs/reviewer_run_01
```

Use a **new output-directory name** for each run. Existing directories are deliberately rejected to protect previous outputs. `primary`, `summary-tables`, `legacy-summary`, `legacy-figures`, and `all` are additional analysis modes; see the component README and command-line help for their output locations. These modes analyze frozen results; they do not execute new model inference or obtain new labels.

For source-archive integrity, after extracting the other two archives:

```sh
cd submission_method_source_supplement_candidate_v1
python3 -B verify_sources.py
cd ../submission_method_source_supplement_A_identity_addendum_v1
python3 -B verify_archive.py
```

## Final diagnostics

After extracting `final_diagnostics.zip`, run:

```sh
cd submission_final_diagnostics_v1
python3 -B reproduce_diagnostics.py --out reviewer_results_01
```

This recalculates the final finite quantities without model, CI-library, dataset or random-number calls. The synthetic task differs from the fixed MAST request: 205 is exact only in the specified family, 197 is a same-task OR-certificate upper bound, and 171 changes the threshold. The 94/5,049 logical-interface result counts deterministic states, not empirical error rates. The original six figures remain available in the base archive; the final main text has five figures and the former runtime figure is supplemental.

## Relating files to the paper

- [FINAL_PAPER_TO_ARTIFACT.csv](FINAL_PAPER_TO_ARTIFACT.csv) supersedes the historically frozen numbering/binding in the component archives. `fast_analysis` includes its original `PAPER_TO_ARTIFACT.csv` and the fixed main, GoEmotions and semantic-reference table inputs. The main table contains 13 rows and 65 reported numeric fields.
- Its `MAST` directory contains the presentation code and outputs. The unique active audit has **50 verified-complete, 2 scientific-error and 4 unknown paths**, retaining all 56 planned paths. NativeProgressive credits **5/8** at budget 300. Costs are conditional on credited completions, not unconditional latency or model-forward estimates.
- The original **45 complete / 11 unknown** audit is retained as history. The amended audit deterministically reverified the same trajectories with the original CI implementation available in its intended import context; it did not rerun acquisitions or choose between old and new outcomes.
- Both retained error histories contain a true-count exclusion although their online and final assertions are correct. Saved-value diagnostics explain the binary64 logical-cap/count-projection mechanism. They are not risk calibration or a refutation of the real-arithmetic statistical method.
- The main-source archive's `METHOD_ENTRYPOINTS.csv`, `inventory/SOURCE_CODE_INDEX.csv`, and `SOURCE_READABILITY_AND_EXECUTION_STATUS.json` locate the original methods, parameters, dependencies and known execution limitations. `EXTERNAL_SOURCE_FETCH_INSTRUCTIONS.txt` identifies pinned external code.

## Reproduction scope

The portable **analysis** entry points above have saved execution evidence. The original CivilComments/GoEmotions CPU replay routes have their necessary frozen inputs and original source pins; a clean-machine full method replay has **not** been run for this release. Some direct source-preparation routes need additional provider files listed in the source archive. The archived full-Native execution route retains its original environment, external-code and one-time authority requirements and is **not** presented as a portable rerun command.

Model weights, original provider text corpora, the historical 703 MB legacy artifact, approximately 8.59 GB of raw trace archives, and the original Native environment are not bundled here. Their availability, original hashes and retrieval requirements are described in the component notices and missing-input inventories. This release therefore does **not** claim complete end-to-end reproduction of every historical or live-inference experiment, or EAB-complete artifacts. Unfinished follow-up experiments supply no results to this release.

## Sources and permissions

Preserve each component's `LICENSE_NOTICES.txt`, dataset citations and dependency notices. This release does not apply a blanket software license to third-party code or data. The archives record the distinct provenance of CivilComments, GoEmotions, MAST and model-reference outputs; a model or upstream-code license is not substituted for a dataset license. No model weights or original Reddit/consumer-complaint text are redistributed here.

The public release contains reproducibility materials. Author-specific CMT declarations, internal scientific reviews and submission administration documents belong to the separate local submission folder and are excluded.

Corresponding author: Xiaolong Shi, xlshi@gzhu.edu.cn.
