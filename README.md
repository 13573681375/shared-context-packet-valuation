# shared-context-packet-valuation

Simulation data and reproducibility code for shared-context receding-horizon packet valuation in connected vehicle platoons.

Companion to **Shared-Context Receding-Horizon Packet Valuation for Connected Vehicle Platoons: Reconstruction and Resource Tradeoffs**.

## Download status

The research-data archive has been prepared and checked locally, but has **not yet been uploaded or independently downloaded from this repository**. A public repository or a checksum file alone is not public access to the research data.

The intended versioned data asset is:

- File: `TRC_reproduction_compact_v1.zip`
- Size: **1,775,635,983 bytes** (approximately 1.78 GB / 1.65 GiB)
- SHA-256: `9dfcda9bac90f37cfa651ecdba9c1134d15aff96fb94bcf1a6b45f6c9c82e280`

When the release is published, download that specific asset from **Releases**. GitHub's automatically generated **Source code (zip)** is not the research-data archive.

## Contents of the prepared archive

- C1: 40,800 candidates and 204,000 valuation steps, including 195,823 accepted reconstructions, 8,177 independent QP fallbacks, full stored target duals, original 212 raw selected-set differences and 15,300 quantized selected-set comparisons.
- C2: all 1,440 retained fixed/optional operating runs (300 + 600 + 540), including unfavourable results, physical exceedances and outliers.
- C3: 30 contexts and 1,950 joint-fleet branches, externalities, joint-selection results and the unsuccessful exploratory surrogate records.
- Original MATLAB sources, configurations, seeds, Python saved-array checks and numerical figure scripts.
- Recorded timing/profiling, stress tests and additional verification records.

The compact archive retains 1,893 original MAT files. Fifty-eight obsolete C1 MAT containers were omitted only after every original dense array and model H/G array was verified as a bit-identical subset of a retained, more complete record. Two original containers remain to satisfy the frozen stress-protocol source hashes. The archive documents the comparison, omissions and four verifier-routing changes. All retained pre-existing scientific MAT/CSV bytes are unchanged.

## Verify and reproduce

After extracting the archive, enter its `TRC_reproduction_compact` directory:

```text
python -m pip install -r requirements.txt
python verify_package.py
python run_saved_verification.py --one runtime
python run_saved_verification.py
python reproduce_data_figures.py
```

Python 3.11+ is recommended. Fresh MATLAB simulations require MATLAB R2021b and Optimization Toolbox. Follow the archive README to prepare a separate source/input workspace; do not run regeneration drivers on the frozen records.

Local checks performed: nine saved-data verification groups, context timestamps, eight reproduced numerical figure panels, package hashes, clean ZIP extraction and a MATLAB dependency/matrix/ZOH check. These are not a new execution of every MATLAB traffic experiment or a new timing benchmark. An independent public-download check remains pending.

## Interpretation

This is a shared-context conditional packet-valuation study, not a demonstrated distributed-network deployment. Accurate local counterfactual reconstruction does not establish universal whole-fleet superiority. Fewer QP calls do not establish wall-clock speedup. The recorded Hybrid/reference p99 times are 105.618/99.655 ms against a 100 ms scheduling period; end-to-end hard-real-time deployment is not established.

## Licensing

Original research data and data documentation are licensed under **CC BY 4.0**; original MATLAB/Python code and software-related scripts are licensed under **MIT**, as authorized by the rights holder on 2026-10-18. These are separate scopes, not a choice of licence for the same file. See [LICENSE](LICENSE), [LICENSING.md](LICENSING.md), and [LICENSES](LICENSES). Third-party materials and external dependencies retain their own terms.

A matching licensed data archive is being prepared; the old checksum identifies the earlier pre-licensing container, not the forthcoming licensed asset.

## Release maintenance

Publish a versioned Release with the named archive and its `.sha256` companion. After publication, verify an unauthenticated download, compare SHA-256 and test the extracted package. Preserve prior versioned assets rather than silently replacing the data used for a submitted result.
